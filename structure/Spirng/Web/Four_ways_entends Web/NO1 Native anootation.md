
Maven
```xml
<dependency>
  <groupId>org.springframework.boot</groupId>
  <artifactId>spring-boot-starter-websocket</artifactId>
</dependency>
```

Configuration
```java
public class WebSocketConfig {

    @Bean
    public ServerEndpointExporter serverEndpoint() {
        return new ServerEndpointExporter();
    }
}
```

```java
public class WsServerEndpoint {
	//连接成功
    @OnOpen
    public void onOpen(Session session) {
        System.out.println("连接成功");
    }
	//连接关闭
    @OnClose
    public void onClose(Session session) {
        System.out.println("连接关闭");
    }
    //接收到消息
    @OnMessage
    public String onMsg(String text) throws IOException {
        return "servet 发送：" + text;
    }
}

```
- @ServerEndpoint
	- Through this spingboot will know the route of app you gives
	- Kind like @RequestMapping
- @OnOpen
	- When websocket-connection established will  trigger the function it annotated, **it has a 'Session' param**
- @OnClose
	- When the connection closed will trigger the function it annotated, **it has a 'Session' param**
- @OnMessage
	- When client send message to server will trigger the function, it has a String entering to show waht params client transpoted
- @OnError
	- when websocket-connection is connecting and an error occured will trigger the function, **it has a 'Session' param**
#### How could server transport messages to client
- Server sending messages must use the 'Session' class, usually in@OnOpen, after connection established  save 'session' in 'Map''s value, key is session's clientId
- Send message will useing key to get session and then send the message out
- could use session.getBasicRemote().sentText() sending message to client





























