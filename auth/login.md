# Auth
***

Returns information about the auth token.

| Endpoint | Description |
| ---- | --------------- |
| [POST /auth/login](/auth/login.md#post-authlogin-auth) | Returns account information for the provided login. |
| [POST /auth/login](/auth/login.md#post-authlogin-info) | Returns account information for the provided auth token. |

## `POST /auth/login (Auth)`

Sending a POST request with the below data returns account information.

| Parameter | Required? | Type | Description |
| ---- | ----- | ---- | ----- |
| login | Yes | string | Username |
| pass | Yes | string | Users Password |
| rememberme | no | unknown | Unknown |

### Example URL

https://www.hitbox.tv/api/auth/login

### Example Response 

Correct credentials:
```json
{
   "user_id":"111",
   "user_name":"test-account",
   "user_logo":"\/static\/img\/channel\/test-account_53aa862ac9adf_large.png",
   "user_logo_small":"\/static\/img\/channel\/test-account_53aa862ac9adf_small.png",
   "user_banned":"0",
   "superadmin":"0",
   "livestream_count":"1",
   "followers":"0",
   "authToken":"123",
   "login":"true",
   "data":{
      "user_id":"111",
      "user_name":"test-account",
      "user_logo":"\/static\/img\/channel\/test-account_53aa862ac9adf_large.png",
      "user_logo_small":"\/static\/img\/channel\/test-account_53aa862ac9adf_small.png",
      "user_banned":"0",
      "superadmin":"0",
      "livestream_count":"1",
      "followers":"0",
      "authToken":"123",
      "login":"true"
   },
   "access":"all"
}
```

Incorrect:
Will return a HTTP 400 Bad Request and response:

```json
auth_failed
```

## `POST /auth/login (Info)`

| Parameter | Required? | Type | Description |
| ---- | ----- | ---- | ----- |
| authToken | Yes | string | User's Auth Token |

### Example URL

https://www.hitbox.tv/api/auth/login

### Example Response 

Correct Auth Token:
```json
{
   "user_id":"111",
   "user_name":"test-account",
   "user_logo":"\/static\/img\/channel\/test-account_53f4e837eb388_large.png",
   "user_logo_small":"\/static\/img\/channel\/test-account_53f4e837eb388_small.png",
   "user_banned":"0",
   "superadmin":"0",
   "livestream_count":"1",
   "followers":"7",
   "authToken":"123",
   "login":"true",
   "data":{
      "user_id":"123",
      "user_name":"test-account",
      "user_logo":"\/static\/img\/channel\/test-account_53f4e837eb388_large.png",
      "user_logo_small":"\/static\/img\/channel\/test-account_53f4e837eb388_small.png",
      "user_banned":"0",
      "superadmin":"0",
      "livestream_count":"1",
      "followers":"7",
      "authToken":"123",
      "login":"true"
   },
   "access":"all"
}
```

Incorrect:
Will return a HTTP 400 Bad Request and response:

```json
auth_failed
```