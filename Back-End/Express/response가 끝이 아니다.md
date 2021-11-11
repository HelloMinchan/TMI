# response가 끝이 아니다

Express로 API를 짤 때 예외 처리에 걸려 응답을 보내는 경우,  
return을 해주지 않으면 excution이 끝나지 않으므로 res 아래의 코드들이 그대로 실행된다..  
이는 의도치 않은 것이므로, 항상 return을 써주자

- ex

```js
router.post("/test", async (req: express.Request, res: express.Response) => {
  if (req.body.key === "예외임") {
    res.status(500).send({ status: "error" });
    return;

    // return res.status(500).send({ status: "error" });는 권장되지 않는다. res반환값이 반환되니까!
  }

  console.log("return 안하면 여기 실행됨!");
  res.send({ status: "success" });
});
```
