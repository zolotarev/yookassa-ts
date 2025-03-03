# Yookassa API для Node.js

Клиент для работы с платежами по API Yookassa. Подходит тем, у кого способ подключения называется API.

## Требования

1. Node.js
2. npm

## Установка

```sh
npm i yookassa-ts
```

## Начало работы

```js
import YooKassa from 'yookassa-ts/lib/yookassa'

const yooKassa = new Yookassa({
shopId: '<Идентификатор магазина>',
secretKey: '<Секретный ключ>'
});

const payment = await yooKassa.createPayment({
amount: {
value: "2.00",
currency: "RUB"
},
payment_method_data: {
type: "bank_card"
},
confirmation: {
type: "redirect",
return_url: "https://www.merchant-website.com/return_url"
},
description: "Заказ №72"
});
```

## API кассы

| Метод            | Описание                                                                    |
| ---              | ---                                                                         |
| `createPayment`  | [Создание платежа](https://yookassa.ru/developers/api#create_payment)       |
| `getPayment`     | [Информация о платеже](https://yookassa.ru/developers/api#get_payment)      |
| `capturePayment` | [Подтверждение платежа](https://yookassa.ru/developers/api#capture_payment) |
| `cancelPayment`  | [Отмена платежа](https://yookassa.ru/developers/api#cancel_payment)         |
| `createRefund`   | [Создание возврата](https://yookassa.ru/developers/api#create_refund)       |
| `getRefund`      | [Информация о возврате](https://yookassa.ru/developers/api#get_refund)      |

## API платежа

### Свойства

| Название              | Описание                                           |
| ---                   | ---                                                |
| `isPending`           | Равен ли статус платежа `pending`                  |
| `isWaitingForCapture` | Равен ли статус платежа `waiting_for_capture`      |
| `isSucceeded`         | Равен ли статус платежа `succeeded`                |
| `isCanceled`          | Равен ли статус платежа `canceled`                 |
| `isResolved`          | Равен ли статус платежа `succeeded` или `canceled` |
| `confirmationUrl`     | URL для подтверждения                              |

### Методы

| Название  | Аргументы | Описание                      |
| ---       | ---       | ---                           |
| `reload`  |           | Получить информацию о платеже |
| `capture` | amount    | Подтвердить платеж            |
| `cancel`  |           | Отменить платеж               |
| `refund`  | amount    | Вернуть платеж                |

## API возврата

### Методы

| Название  | Аргументы | Описание                       |
| ---       | ---       | ---                            |
| `reload`  |           | Получить информацию о возврате |

## История версий
```
0.1.14 @ 24 May 2023  
- Fix usage tips in README  
- Upgrade app version to 0.1.14

0.1.13 @ 22 May 2023  
- Upgrade app version to 0.1.13  
- Release version 0.1.13  
- Fix non required idempotenceKey for createPayment method

0.1.12 @ 22 May 2023  
- Release version 0.1.12  
- Upgrade app version to 0.1.12

0.1.11 @ 22 May 2023  
- Upgrade app version to 0.1.11  
- Release version 0.1.11  
- Fix publish script

0.1.10 @ 22 May 2023  
- Upgrade app version to 0.1.8  
- Release version 0.1.9  
- Fix publish script  
- Release version 0.1.10  
- Upgrade app version to 0.1.10  
- Upgrade app version to 0.1.9  
- Fix publish script  
- Fix publish script

0.1.7 @ 22 May 2023  
- Fix publish script  
- Upgrade app version

0.1.6 @ 22 May 2023  
- Upgrade app version

0.1.5 @ 22 May 2023  
- Upgrade app version

0.1.4 @ 22 May 2023  
- Fix bank_card structure  
- Upgrade app version

0.1.3 @ 21 May 2023  
- Fix publish  
- Fix Amount types  
- Add new build  
- Upgrade app version

0.1.2 @ 21 May 2023  
- Initial commit  
- Restore original logics with injected typings  
- WIP: Add almost all of used types, enums and annotations  
- Initial commit  
- Fix typings in main module, add publish script and changelog  
- Fix publish script  
- Update Readme  
- Refactor YooKassa class  
- Fix version  
- Upgrade app version  
- Fix publish script  
- Fix publish script  
- Update version  
- Update README.md

```

## Контакты

Почта: [dev@its.bz](mailto:dev@its.bz)\
Сайт: [its.bz](https://its.bz)

## Лицензия

MIT
