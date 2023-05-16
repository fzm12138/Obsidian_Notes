## defining a program entry point
```kotlin
fun main(){
	println("hello world")
}
```

```kotlin
fun main(args:Array<String>){
	println(args.contenToString)
}
```

## Functions
- A function with two 'Int' parameters and 'Int' return tyoe
```kotlin
fun sum(a:Int,b:Int):Int{
	retrun a+b
}
```

- A function body can be an expression,It's return type is referred.
```kotlin 
fun sum(a:Int,b:Int)=a+b
```

- Unit return type can be omitted
```kotlin
fun printSum(a:Int,b:Int){
	println("sum of $a and $b is ${a+b}")//sum of -1 and 8 is 7
}
```

## Variabales
- Read-only local variables are defined using the keyword 'val'
- They can be assigned a value only once 
``` kotlin
val a:Int = 1 //immediate assignment
val b = 2 //'Int' type is inferred
val c:Int //Type required when no initializer is provided
c = 3  //deferred assignment 
```

Creating classes and instances
To define a class,use the 'class' keyword
```kotlin
class Shape
```

Properties of a class can be listed in it's declaration or body
```kotlin
Class Rectangle(var height:Double,var length:Double){
	var perimeter = (height+length)*2
}
```

The default constructor with parameters listed in the class declaration is availabel automatically
*(Just like lombok)*
```kotlin
val retangle =Renctangle(5.0,2.0)
println("The perimeter is ${rectangle.perimeter}")
```

Inheritance between classes is declared by a colon( : ).Classes are final by default;to make a class inheritable ,mark it as 'open'
```kotlin
open class Shape

class Rectangle(var height:Double,var length:Double):Shape(){
	var perometer=(heigjt + length) * 2
}
```

Comments:Same as Java

String templates
```kotlin
var a = 1
val s1="a is $a"

a=2
val s2="${s1.replace("is","was")},but now is $a"
// a was 1, but now is 2
```

Conditional experessions
```kotlin
fun maxOf(a:Int,b:Int):Int{
	if(a>b){
		return a
	} else {
		return b
	}
}
```


















































