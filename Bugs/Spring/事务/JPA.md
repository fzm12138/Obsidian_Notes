#### JPA findby 的时候报错： Result must not be null!500
Actually it cause by defalut config JPA
###### Solve:
- Just add @Nullable on the function
```kotlin
@Nullable
fun findOnebyId(id:Int):Student
```
