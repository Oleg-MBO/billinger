**Billinger** - сервис для обработки платежной информации

**Примеры запросов и ответов**

----------
- `GET` /get - Получение информации по балансу пользователя
>Для выполнения этого запроса требуется **токен**

- `Response`
```
{
  "balance": "133.45",
  "flow": [
    {
      "amount": "10",
      "payment_id": 0,
      "date": "2017-30-13T18:30:09Z",
      "direction": "in",
      "cause": "Регистрация аккаунта"
    },
    {
      "amount": "123.45",
      "payment_id": 4794352,
      "date": "2017-30-13T18:30:37Z",
      "direction": "in",
      "cause": "Пополенение аккаунта"
    }
  ]
}
```

- `POST` /create - Генерация формы для пополнения счета
>Для выполнения этого запроса требуется **токен**

- `Request`
```
{
	"amount": 167.78
}
```
- `Response`
```
{
    "id": "48323722",
    "url": "https://api.fondy.eu/api/checkout?token=b46cd3f19"
}
```

- `POST` /verify - Callback для проверки платежа
Платежной системой является Fondy - [api](https://docs.fondy.eu/docs/page/3/)


