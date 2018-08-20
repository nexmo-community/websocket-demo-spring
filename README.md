# Java Websocket Server with Spring

This project demonstrates how to setup a websocket server using [Spring] and [SpringBoot].

- `WebSocketHandler` is used to handle both `TextMessage` and `BinaryMessage` payloads.
- `WebSocketConfiguration` configures the handler to listen on the `/socket` path.

See [#3e8bb33](https://github.com/nexmo-community/websocket-demo-spring/commit/3e8bb33d8136dceab8ef132059d12d00c40b2841) for all changes.

Start the application using `gradle bootRun` it will listen on port `8080` by default.

You can use the following [Nexmo Call Control Object (NCCO)][NCCO] in the [Nexmo Voice Playground] to test if it's working. You should see "New Text Message Received" followed by "New Binary Message Received" in your server console:

```json
[
  {
    "endpoint": [
      {
        "uri": "wss://<your-server-address>/socket",
        "type": "websocket",
        "headers": {
          "app": "demo"
        },
        "content-type": "audio/L16;rate=16000"
      }
    ],
    "action": "connect"
  }
]
```

Be sure to replace `<your-server-address>` with your server's address and, possibly, port number. 

For example: `nexmo.ngrok.io` or `developer.nexmo.com:8080`

[Spring]: https://spring.io
[SpringBoot]: https://spring.io/projects/spring-boot
[Nexmo Voice Playground]: https://dashboard.nexmo.com/voice/playground
[NCCO]: https://developer.nexmo.com/voice/voice-api/ncco-reference