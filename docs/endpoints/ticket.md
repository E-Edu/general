# Ticket API

**This is not the final document and is subject to change**

### `/ticket/create`
This endpoint takes the following  `PUT` request:
```ts
{
    session: Guid,
    task_id : Guid
    title: String,
    body: String,
}
```

#### Responses:

```ts
{
    error: String|null
}
```
This response will return `null` in case the creation of a ticket was successful and a `String` in case a [Error](errors.md) ocurred.

---
### `/ticket/delete`
This endpoint takes the following `DELETE` request

```ts
{
    session: Guid,
    ticket_id: Guid,
}
```

#### Responses:

```ts
{
    error: String|null
}
```
The response will return `null` in case the  deletion was successful and a `String` in case a [Error](errors.md) ocurred.

---
### `/ticket/list`

This endpoint takes the following  `POST` request:

```ts
{
    session: Guid
}
```
#### Responses:

```ts
{
    tickets: [{
        ticket_id: Guid,
        task_id: Guid,
        sender: Guid,
		title: String,
		body: String
	}]|null
}
```
This response will return `null` in case no ticket to process exists.

---

### `/ticket/edit`

This endpoint takes the following `PUT` request:

```ts
{
    session: Guid,
    ticket_id: Guid,
    comment: String,
    is_Troll: Boolean
}
```

#### Responses:

```ts
{
    error: String|null
}
```
The response will return `null` in case the edit was successful and a `String` in case a [Error](errors.md) ocurred.
