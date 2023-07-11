### 接口地址
http://101.200.242.236:8888/sdk/updateWormDeviceParams
### 请求方式
- POST
- application-json
### 返回格式
```kotlin
class WormUpdateParamEntity {
    //设备地址码
    var deviceAddr: String? = null
    //请求数据域
    val dicts: List<Dicts> = ArrayList()

    class Dicts{
        var name:String?=null
        var value:String?=null
    }
}
```