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

