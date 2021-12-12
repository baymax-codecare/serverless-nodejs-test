
### Deployment

Install dependencies with:

```
npm install
```

and then deploy with:

```
serverless deploy
```

### Invocation

After successful deployment, you can create a new user by calling the corresponding endpoint:

```bash
curl --request POST 'https://xxxxxx.execute-api.us-east-1.amazonaws.com/users' --header 'Content-Type: application/json' --data-raw '{"email": "test@test.com", "name": "John"}'
```

Which should result in the following response:

```bash
{"email":"test@test.com", "name":"John"}
```

You can later retrieve the user by `email` by calling the following endpoint:

```bash
curl https://xxxxxxx.execute-api.us-east-1.amazonaws.com/users/email
```

Which should result in the following response:

```bash
{"email":"test.test.com","name":"John"}
```

If you try to retrieve user that does not exist, you should receive the following response:

```bash
{"error":"Could not find user with provided \"email\""}
```
