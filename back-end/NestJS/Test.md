기본적으로 jest 환경 보일러 플레이팅 되어있음.

.spec.ts 파일만 만들면  
npm run test:~ 명령어로 테스팅 가능

- 유닛 테스트 : 함수 단위 테스팅
- e2e(end-to-end) 테스트 : 전체 시스템 테스팅

describe : 테스트 정의  
beforeEach : 테스트를 하기 전에 실행되는 로직  
it : 개별 테스트 정의

```js
describe("AppController (e2e)", () => {
  let app: INestApplication;

  beforeEach(async () => {
    const moduleFixture: TestingModule = await Test.createTestingModule({
      imports: [AppModule],
    }).compile();

    app = moduleFixture.createNestApplication();
    /*
     테스트 환경과 실제 환경세팅을 동일하게 해야 함.
     테스트 환경에서 transform 설정을 하지 않으면,
     test 환경에서 URL을 number로 바꿔주지 않기에 string 타입으로 됨.
     따라서 잘못된 테스팅이 될 수 있음.
    */
    app.useGlobalPipes(
      new ValidationPipe({
        whitelist: true,
        forbidNonWhitelisted: true,
        transform: true,
      })
    );
    await app.init();
  });

  it("/ (GET)", () => {
    return request(app.getHttpServer())
      .get("/")
      .expect(200)
      .expect("Welcome to my Movie API");
  });

  it("/movies (GET)", () => {
    return request(app.getHttpServer()).get("/movies").expect(200).expect([]);
  });

  describe("/movies", () => {
    it("DELETE", () => {
      return request(app.getHttpServer()).delete("/movies").expect(404);
    });
  });
});
```
