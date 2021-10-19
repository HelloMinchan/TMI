data transfer object(DTO)

**사용 이유** <br>

1. 코드 자동완성 (오타 방지)
2. request 데이터의 Validation

NestJS에서는 파이프라는 개념을 이용<br>
class-validator class-transformer 라이브러리 사용

```js
app.useGlobalPipes(
  new ValidationPipe({
    whitelist: true,
    forbidNonWhitelisted: true,
    transform: true,
  })
);
```

```js
import { IsString, IsNumber } from 'class-validator';

export class CreateMovieDto {
  @IsString()
  readonly title: string;
  @IsNumber()
  readonly year: number;
  @IsString({ each: true })
  readonly genres: string[];
}

```
