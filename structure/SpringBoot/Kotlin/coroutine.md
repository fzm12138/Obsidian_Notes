- Essentialy it's lightweight thread
- Kotlin supplies a kind of advanced-construct(suspend function) and a library`kotlinx.coroutines` in order to make most programmers get used to the  asynchronous program(Which is similar to normal program)
	- regarded it as Kotlin excute `async/await` style,this style could use in other languages
- This is how to using suspend function in `kotlinx.coroutines` and the constructor of the library working:
```kotlin
suspend fun coroutines () : CombinedResult = coroutineScope {
	//Returns a String directly, no future object
	val orderId: String = fetchMostRecentOrderId()
 
	//Note the Deferred type indicating this is a future
	val deliveryCostFuture: Deferred<String> = async { fetchDeliveryCost(orderId) }
	val stockInformationFuture: Deferred<String> = async { fetchStockInformation(orderId) }
	
	//Awaiting for completion of previous parallel executed fuctions
	CombinedResult(deliveryCostFuture.await(), stockInformationFuture.await())
}
 
suspend fun fetchDeliveryCost () : String { ... }
suspend fun fetchStockInformation () : String { ... }
```
- Kotlin coroutine is in order default,but js coroutine is concurrency in default



