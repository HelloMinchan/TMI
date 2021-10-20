# DTO (data transfer object)

**사용 이유** <br>

1. 코드 자동완성 (오타 방지)
2. request 데이터의 Validation

NestJS에서는 파이프라는 개념을 이용<br>
class-validator class-transformer 라이브러리 사용
partial update에는 @nestjs/mapped-types 사용

<br>

- 파이프라인 적용

```js
app.useGlobalPipes(
  new ValidationPipe({
    whitelist: true,
    forbidNonWhitelisted: true,
    transform: true,
  })
);
```

- 일반적인 DTO

```js
export class CreateMovieDto {
  export class CreateMovieDto {
  @IsString()
  readonly title: string;
  @IsNumber()
  readonly year: number;
  @IsOptional()
  @IsString({ each: true })
  readonly genres: string[];
}
}

```

- Partial Type 적용

```js
export class UpdateMovieDto {
  @IsString()
  readonly title?: string;
  @IsNumber()
  readonly year?: number;
  @IsString({ each: true })
  readonly genres?: string[];
}

// 위와 같은 동작을 함
export class UpdateMovieDto extends PartialType(CreateMovieDto) {}
```
