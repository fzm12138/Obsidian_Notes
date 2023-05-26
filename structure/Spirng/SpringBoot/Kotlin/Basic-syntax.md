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

*Comments:Same as Java*

**String templates**
```kotlin
var a = 1
val s1="a is $a"

a=2
val s2="${s1.replace("is","was")},but now is $a"
// a was 1, but now is 2
```

**Conditional experessions**
```kotlin
:Int{
	if(a>b){
		return a
	} else {
		return b
	}
}
```
also
```kotlin
fun maxOf(a:Int,b:Int) = if(a>b) a else b
```

## loop
#### for loop
```kotlin
val items = listOf("apple","banana","kiwifruit")
for(item:items){
	println(item)
}
```
or
``` kotlin
val items = listOf("apple","banana","kiwifruit")
for(index in items.indices){
	println("item at $index is ${items[index]}")
}
```


### when expression
```kotlin
fun describe(obj : Any):String =
	when (obj){
		1          -> "One"
        "Hello"    -> "Greeting"
        is Long    -> "Long"
        !is String -> "Not a string"
        else       -> "Unknown"
	}
```

### Ranges
check a number is within a range using 'in'
```kotlin
val x=10
vay y=9
if(x in 1...y+1){
	println("fits in range")
}
```

Also,it can check if a number is out of range
```kotlin
val list = listOf("a","b","c")
if(-1 !in 0...list.lastIndex){
	println("-1 is out of range")
}
if(list.size !in list.indices){
	println("list size is out of valid list indices range, too")
}
```

it could over a progression
```kotlin
for(x in 1... 10 step 2){
	print(x)
}//13579
for(x in 9 downTo 0 step 3){
	print(x)
}//9630
```

## Collections
Iterate over a collection
```kotlin
for(item in items){
	println(item)
}
```

Check if a collection contains an object using `in` operator.
```kotlin
when{
   "orange" in items -> println("juicy")
    "apple" in items -> println("apple is fine too")
}
```

Using lambda expressions to filter and map collections:
```kotlin
val fruits = listOf("banana","avocado","apple","kiwifruit")
fruits
	.filter{ it.startsWith("a") }
	.sortedBy{ it }
	.map{ it.uppercase() }
	.forEach{ println(it) }
```

## Nullable values and null checks
- **A reference must be explicitly marked as nullable when `null`value is possible.**
- Nullable type names have `?` at the end
- Return `null` if `str` does not hold an integer
```kotlin
fun parseInt(str: String): Int? { // ... }
```
Use a function returning nullable value:
```kotlin
fun printProduct(arg1: String, arg2: String) {
    val x = parseInt(arg1)
    val y = parseInt(arg2)

    // Using `x * y` yields error because they may hold nulls.
    if (x != null && y != null) {
        // x and y are automatically cast to non-nullable after null check
        println(x * y)
    }
    else {
        println("'$arg1' or '$arg2' is not a number")
    }    
}
```

### Type checks and automatic casts
- The `is` operator checks if an expression is an instance of a type.
- if an immutable local variable or property is checked for a specific type,there's no need to cast it explicitly
```kotlin
fun getStringLength(obj: Any): Int? {
    if (obj is String) {
        // `obj` is automatically cast to `String` in this branch
        return obj.length
    }

    // `obj` is still of type `Any` outside of the type-checked branch
    return null
}
```
or
```kotlin
fun getStringLength(obj: Any): Int? {
    if (obj !is String) return null

    // `obj` is automatically cast to `String` in this branch
    return obj.length
}
```
or even
```kotlin
fun getStringLength(obj: Any): Int? {
    // `obj` is automatically cast to `String` on the right-hand side of `&&`
    if (obj is String && obj.length > 0) {
        return obj.length
    }​
    return null
}

```


- Add`!!`after  variable and if the variable is null will throws NullPointException
- Add`?` after variable means the very variable could be null



















	


























































