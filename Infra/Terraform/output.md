# output

테라폼으로 AWS 인프라를 구축하다가  
Security Group을 어떻게 모듈화할까 고민이 되었다.

모듈로 따로 빼고 싶은데 Security Group은 id가 여러군데에서 또 참조되어 쓰이기 때문이다.

해답은 output이었다.

```hcl
output "id" {
  value = aws_security_group.security_group.id
}
```

이렇게 output을 만든뒤 참조 모듈에서

```hcl
module "security_group" {
  source = "../security_group"
}

... {
    vpc_security_group_ids = [module.security_group.id]
}
```

이런식으로 적용했다.
