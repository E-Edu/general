# Task API

**This is not the final document and is subject to change**

### `/task/create`
This endpoint takes the following `POST` body:
```ts
{
    isFinalTask : Boolean,
    session : Guid,
    task : String,
    taskType : String,
    necessaryPoints : Number,
    subject : String,
    module : String,
    lecture : String,
    difficulty : String
}
```

#### Responses:

```ts
{
    error: String|null
}
```
The response will return `null` in case the task creation was successful and a `String` in case a [Error](errors.md) ocurred.

---

### `/task/search`
This endpoint takes the following `POST` body:
```ts
{
    session : Guid,
    subject : String,
    module : String,
    lecture : String,
}
```

#### Responses: 

```ts
{
    tasks: [{
        task : String,
        taskType : String,
        necessaryPoints : Number,
        subject : String,
        module : String,
        lecture : String,
        difficulty : String,
		author : Guid
	}],
    error: String|null
}
```

If `error` is set to `null`, the search was successful.
The response will return a list of tasks in case the search was successful and a error `String` in case a [Error](errors.md) ocurred.


---

### `/task/verify`
This endpoint takes the following `POST` body:
```ts
{
    session : Guid,
    taskId : Number
}
```

#### Responses: 

```ts
{
    error: String|null
}
```

The response will return `null` in case the verification was successful and a `String` in case a [Error](errors.md) ocurred.

---

### `/task/getPendingTasks`
This endpoint takes the following `POST` body:
```ts
{
    session : Guid
}
```

#### Responses: 

```ts
{
    error: String|null
}
```

The response will return `null` in case the request was successful and a `String` in case a [Error](errors.md) ocurred.


---


### `/task/getNext`

This endpoint is used to get the next task, that is based on the last task, to continue with more tasks in that context. Eventually this will return a final task. 

This endpoint takes the following `POST` body:

```ts
{
    session : Guid,
	last_task_id: Number
}
```

#### Responses: 

```ts
{
    new_task :
    {
        isFinalTask : Boolean,
        task : String,
        taskType : String,
        necessaryPoints : Number,
        subject : String,
        module : String,
        lecture : String,
        difficulty : String,
		author : Guid
	}
    error: String|null
}
```

The response will return `null` in case the request was successful and a `String` in case a [Error](errors.md) ocurred.