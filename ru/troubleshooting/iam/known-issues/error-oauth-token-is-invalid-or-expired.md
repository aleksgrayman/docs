# Устранение ошибки OAuth token is invalid or expired


## Описание проблемы {#issue-description}

Истек срок действия OAuth-токена, появилась ошибка `OAuth token is invalid or expired`.

## Решение {#issue-resolution}

Срок действия OAuth-токена составляет 1 год – он мог быть отозван по истечении этого периода.

Возможно, для учетной записи, которой принадлежал токен, был изменен пароль или способ аутентификации. Список причин, из-за которых токен мог утратить свою актуальность, приведен [здесь](https://yandex.ru/dev/id/doc/dg/oauth/reference/token-invalidate.html).

Для работы YC CLI рекомендуем использовать аутентификацию через сервисный аккаунт с необходимыми ролями при помощи авторизованного ключа. Мы подробно описали процесс настройки в этой [статье](../../../cli/operations/authentication/service-account.md).

Авторизованный ключ не имеет срока годности, и пользователь должен хранить его самостоятельно. Если кто-то мог узнать ваш секретный ключ, его нужно удалить. Подробнее об этом способе аутентификации пишем в [документации](../../../iam/concepts/authorization/key.md).