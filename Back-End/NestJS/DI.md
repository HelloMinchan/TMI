# DI (Dependency Injection)

의존성 주입  
**Module**에 **controllers**와 **providers**를 설정하고,  
**Controller**에 **Service**를 주입함.

이를 통해, 관심사 분리가 가능해짐.  
Service의 default scope는 싱글톤이지만, 커스터마이즈 가능함.

- Module

```js
@Module({
  controllers: [MoviesController],
  providers: [MoviesService],
})
export class MoviesModule {}
```

- Service

```js
@Injectable() // 클래스를 Injectable하게 만드는 데코레이터 (싱글톤 객체로 메모리상에 존재하게 됨)
export class MoviesService {
  private movies: Movie[] = [];

  getAll(): Movie[] {
    return this.movies;
  }

  getOne(id: number): Movie {
    const movie = this.movies.find((movie) => movie.id === +id);

    if (!movie) {
      throw new NotFoundException(`movie id is not found ${id}`);
    }

    return movie;
  }

  deleteOne(id: number) {
    this.getOne(id);
    this.movies = this.movies.filter((movie) => movie.id !== id);
  }

  create(movieData: CreateMovieDto) {
    this.movies.push({
      id: this.movies.length + 1,
      ...movieData,
    });
  }

  update(id: number, updateData: UpdateMovieDto) {
    const movie = this.getOne(id);
    this.deleteOne(id);

    this.movies.push({ ...movie, ...updateData });
  }
}

```

- Controller

```js
@Controller('movies')
export class MoviesController {
  // 생성자에서 의존성 주입을 함에 따라, 아래 메소드들에서 서비스 사용 가능함
  constructor(private readonly moviesService: MoviesService) {}

  @Get()
  getAll(): Movie[] {
    return this.moviesService.getAll();
  }

  @Get(':id')
  getOne(@Param('id') movieId: number): Movie {
    console.log(typeof movieId);
    return this.moviesService.getOne(movieId);
  }

  @Post()
  create(@Body() movieData: CreateMovieDto) {
    return this.moviesService.create(movieData);
  }

  @Delete(':id')
  remove(@Param('id') movieId: number) {
    return this.moviesService.deleteOne(movieId);
  }

  @Patch(':id')
  patch(@Param('id') movieId: number, @Body() updateData: UpdateMovieDto) {
    return this.moviesService.update(movieId, updateData);
  }
}
```
