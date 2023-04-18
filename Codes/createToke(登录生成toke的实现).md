```java
/**  
* 创建令牌  
*  
* @param loginUser 用户信息  
* @return 令牌  
*/  
public String createToken(LoginUser loginUser)  
{  
String token = IdUtils.fastUUID();  
loginUser.setToken(token);  
setUserAgent(loginUser);  
refreshToken(loginUser);  
  
Map<String, Object> claims = new HashMap<>();  
claims.put(Constants.LOGIN_USER_KEY, token);  
return createToken(claims);  
}
```