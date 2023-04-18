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

```java
/**  
* 从数据声明生成令牌  
*  
* @param claims 数据声明  
* @return 令牌  
*/  
private String createToken(Map<String, Object> claims)  
{  
String token = Jwts.builder()  
.setClaims(claims)  
.signWith(SignatureAlgorithm.HS512, secret).compact();  
return token;  
}
```