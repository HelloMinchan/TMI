Express의 Router와 같음<br>
URL 받아와서 실행할 함수를 매핑함

```js
@Controller('movies')
export class MoviesController {
  constructor(private readonly moviesService: MoviesService) {}

  // Req, Res는 Fastify에선 사용 못하므로 최대한 지양
  @Get()
  getAll(@Req() req, @Res() res): Movie[] {
    return this.moviesService.getAll();
  }
  // 같은 HTTP METHOD라서 id 보다 위에 두어야 함
  @Get('/search')
  search(@Query('year') searchingYear: string) {
    return this.moviesService.search(searchingYear);
  }

  @Get(':id')
  getOne(@Param('id') movieId: string): Movie {
    return this.moviesService.getOne(movieId);
  }

  @Post()
  create(@Body() movieData) {
    return this.moviesService.create(movieData);
  }

  @Delete(':id')
  remove(@Param('id') movieId: string) {
    return this.moviesService.deleteOne(movieId);
  }

  @Patch(':id')
  patch(@Param('id') movieId: string, @Body() updateData) {
    return this.moviesService.update(movieId, updateData);
  }
}
```
