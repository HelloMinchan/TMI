Service 뒷단에 붙는 데이터베이스 제어 패턴

Service에 Repository를 주입시켜 DB 제어 관심사 분리를 한다.

- Module

```js
@Module({
  imports: [TypeOrmModule.forFeature([UserRepository])],
  controllers: [UserController],
  providers: [UserService],
})
export class UserModule {}
```

- Service

```js
@Injectable()
export class UserService {
  constructor(
    @InjectRepository(UserRepository)
    private UserRepository: UserRepository,
  ) {}

  async getBook(user_id: string): Promise<User> {
    const data = await this.UserRepository.findOne({ user_id: user_id });

    return data;
  }
}
```
