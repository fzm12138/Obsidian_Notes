#### 定义变量
```js
var x=5+6;
//
var a,length;
a=5;
length=4;
```

#### 分号分隔语句
```js
var x=5+6;
```

#### 数据类型
```js
var length=5; //number
var points=x*10;//number
var lastName="Peter";//String
var cars=["ss","bb"];//Array
var person={rows:"sensor",columns:"211"};//Object
```

#### 函数
```js
function myFunction(a,b){
return a*b;
}
```

#### 对象
- js的对象是拥有属性和方法的数据
```js
var car="fiat";

```
- 对象也是变量，可以包含多个值
	- 以name : value对呈现
```js
var car={name:"ff",model:100,color:"white"}
```
##### 可以通过两种方式访问对象属性
```js
var person={lastName:"kk"};

//第一种
person.lastName;

//第二种
person["lastName"];
```

#### 对象方法
- 对象的方法定义了一个函数，并作为对象的属性存储
- 对象方法通过添加()调用
```js
name=person.fullName();
```
##### 访问对象方法
```js
methodName:function(){
//代码块 
}

objectName.methodName()
```

函数
```js
function myFunction(){
	alert("xx");
}

//把参数当成变量来声明
function my2(var1,var2){
	return var1+var2;
}
```

#### 字符串
```js
var carname="kkxx1"
var character=carname[2];
```



































