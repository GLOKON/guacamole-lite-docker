# guacamole-lite-docker

## Synopsis
 (From: https://github.com/vadimpronin/guacamole-lite)
 
*guacamole-lite* is a NodeJS replacement for *guacamole-client* (server-side Java servlet).
Guacamole is a RDP/VNC client for HTML5 browsers.

This is the best solution for those ones who need to integrate Guacamole into an existing projects with their own users
and connections management (or without them at all).

This diagram describes the architecture of Guacamole and the role of *guacamole-lite* in it:
![arch](https://cloud.githubusercontent.com/assets/5534215/25705792/3140af24-30e7-11e7-99a0-0f77c5bf2e73.png)

## Installation
This will start a WebSocket tunnel on port 8080 with the secret key T0a5t3r.

**NOTE:** Please use a secure secret key for your deployment

```
docker run -e CRYPT_SECRET=T0a5t3r -e GUACD_HOST=127.0.0.1 -e GUACD_PORT=4822 -d -p 8080:8080 glokon/guacamole-lite-docker
```

## Options
Below are the available options exposed as environment variables to the container.

You can override by appending the following to the `docker run` command

```
-e VARIABLE_NAME=OVERRIDEN_VALUE
```

| Variable | Default | Values  |
|---|---|---|
| `CRYPT_SECRET`| No Default | Shared Secret | 
| `CRYPT_CYPHER` | `AES-256-CBC` | Any supported Node crypto algorithm |
| `GUACD_HOST` | `127.0.0.1` | Host address of guacd |
| `GUACD_PORT` | `4822` | Port of guacd |
