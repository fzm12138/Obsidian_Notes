## setter&getter
- using **val** won't generate 'setter'
- using **var** will generates 'setter'
- if there's no need to auto-generate getter and setter
	- Using **@JvmField** on attribute
```kotlin 
data class Child(
    @JvmField
    var age: Int,//won't generate getter and setter,and it will be public
    var name: String
)
```

##### customized getter&setter
```kotlin
data class Child(
    @get:JvmName("studentAge")
    var age: Int,
    @set:JvmName("studentName")
    var name: String
)

```

##### constructor
Normaly after compiling `data class` will auto generate a constructor contains all attributes
- Using @JvmOverloads
```kotlin
data class Child @JvmOverloads constructor(
    var age: Int,
    var name: String = ""
)//will generate 2 constuctors
```

##### componentN()
Kotlin has a proper noun `destructuring declarations`
```kotlin
data class Child(
    val age: Int,
    val name: String,
    val nickName: String
)

fun main() {
    val child = Child(30, "张三丰", "小张")
    val(studentAge, studentName) = child
    println(studentAge)//30
    println(studentName)//张三丰
}
```
decompile:
```java
public final class ChildKt {
   public static final void main() {
      Child child = new Child(30, "张三丰", "小张");
      int studentAge = child.component1();
      String studentName = child.component2();
      System.out.println(studentAge);
      System.out.println(studentName);
   }

   // $FF: synthetic method
   public static void main(String[] var0) {
      main();
   }
}
```
if u don't need the second element
```
fun main() {
    val child = Child(30, "张三丰", "小张")
    val(studentAge, _, studentNickName) = child
    println(studentAge)
    println(studentNickName)
}

```









