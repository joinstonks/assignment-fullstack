# Stonks backend assignment

**`You are free to use any backend stack only PostgreSQL as database`**

Use this `Profile` schema and **don't modify it**

| key         | type        | unique |
| ----------- | ----------- | :----: |
| `id`        | _uuid_      |   -    |
| `fullName`  | _string_    |   -    |
| `username`  | _string_    |  yes   |
| `email`     | _string_    |  yes   |
| `avatar`    | _string_    |   -    |
| `active`    | _boolean_   |   -    |
| `createdAt` | _timestamp_ |   -    |
| `updatedAt` | _timestamp_ |   -    |

## API fonctionnalities

You will write routes that do the following fonctionnalities and handle auth.

- Signup/connect with email
- Signup/connect with OAuth2 Google
- Fetch/update a profile
- Add 2fa to a profile
- Follow/unfollow a profile
- Push notifications
- Start a stream -> Push notifications to followers or send emails if users is offline.
- Create a channel

## Websockets

Each users can create a channel, the owner is the `HOST` of the channel.

Each channels has a livechat where unauth and authenticated users can receive messages.

#### Fonctions that the backend need to perform from messages

- /set admin @user : add role `ADMIN` to @user only `HOST` can do that
- /unset admin @user : remove role `ADMIN` to @user only `HOST` can do that
- /mute @user
- /unmute @user
- /ban @user
- /unban @user
- /suspend : will suspend the channel and can only be perform by `SUPERADMIN`
- /set title "title name" : Update channel title
- /set description "description ... " : Update channel description

### Roles

Here is the minimum 3 roles: `SUPERADMIN / HOST / ADMIN`

- `SUPERADMIN` are high level role, only stonks staff can be SUPERADMIN.

- `HOST` can perform actions in chat messages.

- `SUPERADMIN` are high level role, only stonks staff can be SUPERADMIN.

### Bonus

- `Swagger` and make a beautiful documentation
- `Webhooks` the host can add a webhook endpoint, and once activated will broadcast all events from chat channel to the endpoint.
- `Redis` for queuing webhooks
