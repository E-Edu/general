# User API

**This is not the final document and is subject to change**

### `/user/register`
This endpoint takes the following `POST` body:
```ts
{
    email: String,
    password: String,
    name: String,
    teacher_token: String|null
}
```
*Notice that Passwords should be stored by being hashed with [BCrypt](https://en.wikipedia.org/wiki/Bcrypt).*

#### Responses:
```ts
{
    error: String|null
}
```
The response will return `null` in case the registration was successful and a `String` in case a [Error](errors.md) ocurred.

After processing this request a email will be dispatched to the users email address,
containing a link for verifying their account structured in the following way:
`https://DOMAIN.TLD/verify?token=$TOKEN`

In case the teacher token isn't `null` and valid the teacher is instantly verified and marked as teacher.

---

### `/user/verify`
This endpoint takes the following `PATCH` arguments:
```ts
{
    token: String
}
```

#### Responses:
```ts
{
    error: String|null,
    session: Guid|null
}
```

If [`error`](errors.md) is set to `null`, the user was successfully verified and a session has been created

---

### `/user/login`
This endpoint takes the following `POST` body:
```ts
{
    email: String,
    password: String
}
```
*Notice that Passwords should be stored by being hashed with [BCrypt](https://en.wikipedia.org/wiki/Bcrypt).*

#### Responses:
```ts
{
    error: String|null,
    session: Guid|null
}
```
The response will return the session `Guid` in case the verification was successful and a error `String` in case a [Error](errors.md) ocurred.

---

### `/user/info`
This endpoint takes the following `POST` body:
```ts
{
    session: Guid,
    user: Guid|null
}
```
If `user` is set to `null` information about the owner of the Session is returned,
otherwise information of the requested `user` is provided, if the session owner has the right permission to request them.

#### Responses:
```ts
{
    error: String|null,
    teacher: Boolean,
    admin: Boolean,
    privileged_student: Boolean,
    report_spammer: Number
}
```
If[`error` is set to `null`, the login was successful.
The response will return privilege flags of the requested User in case the verification was successful and a error `String` in case a [Error](errors.md) ocurred.
`report_spammer` will always return 0 unless the session owner has the correct rights

---

### `/user/update`
This endpoint takes the following `PUT` body:
```ts
{
    session: Guid,
    user: Guid|null,
    teacher: Boolean|null,
    admin: Boolean|null,
    privileged_student: Boolean|null,
    report_spammer: Boolean|null
}
```
The specified `user` if not `null` (then the owner of the session) will have their flags altered, if the owner of the session has the right permission.
A user can NEVER alter their own `report_spammer`!

#### Responses:
```ts
{
    error: String|null
}
```
If `error` is set to `null`, the operation was successful.

