# Scrivener

Acts as a helper between XMPP and HipChat so that when an XMPP client mentions a user's name, that mention is converted to a HipChat-style "mention" so that the user being mentioned is actually notified.

This shouldn't be necessary. If you find this bot as annoying as I do, please [vote for HipChat to fix their XMPP support](http://help.hipchat.com/forums/138883-suggestions/suggestions/2979786-xmpp-group-chat-nicknames).

![Example screenshot](example.png)

## Prerequisites

Scrivener requires an API `auth_token` with **admin** privileges. When referencing a room, use the actual room name like "API" or "Platform Incidents".

## Run Locally

```
gem install foreman
vi .env # add AUTH_TOKENS and ROOMS
foreman start
```

## Platform Deploy

```
heroku create
heroku config:add AUTH_TOKENS=
heroku config:add ROOMS=
git push heroku master
heroku ps:scale worker=1
```

Note that both `AUTH_TOKENS` and `ROOMS` are limited to one entry each until this bot has been battle tested a little more.
