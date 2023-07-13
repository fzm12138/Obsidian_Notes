```java
package com.example.dsdigital.service

import com.alibaba.druid.support.json.JSONUtils
import com.alibaba.fastjson.JSON
import com.example.dsdigital.consts.ConstTime
import com.example.dsdigital.model.worm.PicReceiveEntity
import com.example.dsdigital.model.worm.WormLoginEntity
import com.example.dsdigital.model.worm.WormRealTimeEntity
import com.example.dsdigital.repository.WormLoginRepository
import com.example.dsdigital.repository.WormRealTimeRepository
import com.example.dsdigital.utils.TimeUtils
import com.google.gson.Gson
import jakarta.annotation.PostConstruct
import lombok.RequiredArgsConstructor
import lombok.extern.slf4j.Slf4j
import org.springframework.stereotype.Component
import org.springframework.stereotype.Service
import java.time.LocalDateTime
import java.time.temporal.ChronoUnit

/**
 * @author fzm
 * @since 2023-07-12
 * **/
@Service
@RequiredArgsConstructor
@Component
@Slf4j
class WormService(
    private val wormLoginRepository: WormLoginRepository, private val wormRealTimeRepository: WormRealTimeRepository
) {
    var compareTime: LocalDateTime? = null

    /**
     * 每次服务重启都运行一次，以保证数据的正确保存
     * **/
    @PostConstruct
    private fun run() {
//        if (ChronoUnit.MINUTES.between(wormRealTimeRepository.findFirstByDeviceAddr().updateTime, LocalDateTime.now()) > 60) {
//            this.compareTime = LocalDateTime.now().minusHours(2)
//        }else{
//            this.compareTime=LocalDateTime.now()
//        }
    }

    /**
     * 图片上传
     * @param jsonMap map形式保存的参数
     * **/
    fun picReceive(jsonMap: Map<String?, Any?>) {
        val picReceiveEntity = picAssign(jsonMap)
    }

    private fun picAssign(jsonMap: Map<String?, Any?>): PicReceiveEntity {
        val picReceiveEntity: PicReceiveEntity = PicReceiveEntity()
        picReceiveEntity.deviceAddr = jsonMap["deviceAddr"].toString()
        picReceiveEntity.file = jsonMap["file"].toString()
        picReceiveEntity.datetime = jsonMap["datetime"].toString()
        return picReceiveEntity
    }

    /**
     * 登录
     * @param deviceAddr 设备地址
     * @param type 类型
     * **/
    fun login(jsonMap: Map<String, Any>) {
        val wormLogin = loginAssign(jsonMap)
        wormLoginRepository.save(wormLogin)
    }

    private fun loginAssign(jsonMap: Map<String, Any>): WormLoginEntity {
        val wormLogin: WormLoginEntity = WormLoginEntity()
        wormLogin.deviceAddr = jsonMap["deviceAddr"].toString()
        wormLogin.type = jsonMap["type"].toString()
        wormLogin.time = LocalDateTime.now()
        return wormLogin
    }

    /**
     * 实时数据推送
     * @param deviceAddr 设备地址
     * @param type 类型
     * @param data 数据域
     * **/
    fun getRealTimeData(map: Map<String, Any>) {
        println(LocalDateTime.now().toString())
        println(LocalDateTime.now().toString())
        println(LocalDateTime.now().toString())
        println(LocalDateTime.now().toString())
        println(LocalDateTime.now().toString())
        println(LocalDateTime.now().toString())
        println(LocalDateTime.now().toString())
        println(LocalDateTime.now().toString())
        println(LocalDateTime.now().toString())
        println(LocalDateTime.now().toString())
        println(LocalDateTime.now().toString())
        val gson: Gson = Gson()
        val dataMap: Map<*, *> = JSON.parseObject(JSONUtils.toJSONString(map["data"]))
        val wormRealTimeEntity = gson.fromJson(
            JSONUtils.toJSONString(map), WormRealTimeEntity::class.java
        )
        println("nothing happened yet")
        println("nothing happened yet")
        println("nothing happened yet")
        println("nothing happened yet")
        println("nothing happened yet")
        println("nothing happened yet")
        assignAndSave(dataMap, wormRealTimeEntity)
    }

    /**
     * toboolean
     * toFloat
     * **/
    private fun assignAndSave(dataMap: Map<*, *>, wormRealTimeEntity: WormRealTimeEntity) {
        println("dtime")
        println("dtime")
        println("dtime")
        println("dtime")
        println("dtime")
        println("dtime")
        wormRealTimeEntity.data?.runHour = dataMap["runhour"].toString()
        wormRealTimeEntity.data?.leadWormTime = dataMap["leadwormtime"].toString()
        wormRealTimeEntity.data?.dryingTime = TimeUtils.timeStamp2Date(dataMap["dtime"].toString())

//        wormRealTimeEntity.updateTime = LocalDateTime.now()
        wormRealTimeEntity.data?.insecticidalControl = dataMap["dryingtemperature"].toString() != "0"
        wormRealTimeEntity.data?.workingMode = dataMap["workingmode"].toString() != "0"
        wormRealTimeEntity.data?.insectRainBaffle = dataMap["insectrainbaffle"].toString() != "0"
        wormRealTimeEntity.data?.dryingControl = dataMap["dryingcontrol"].toString() != "0"
        wormRealTimeEntity.data?.fillLight = dataMap["filllight"].toString().toBoolean()
        wormRealTimeEntity.data?.dryingTaffle = dataMap["dryingtaffle"].toString() != "0"
        wormRealTimeEntity.data?.dryingTemperatureDifference =
            dataMap["dryingtemperaturedifference"].toString().toFloat()
        wormRealTimeEntity.data?.afterRainDelayTime = dataMap["afterraindelaytime"].toString()
        wormRealTimeEntity.data?.insecticidalTemperatureReal =
            dataMap["insecticidaltemperaturereal"].toString().toFloat()
        wormRealTimeEntity.data?.rainFall = dataMap["rainfall"].toString()
        wormRealTimeEntity.data?.trapLampTime = dataMap["traplamptime"].toString()
        println("beginTime")
        println("beginTime")
        println("beginTime")
        println("beginTime")
        println("beginTime")
        println("beginTime")
        println("beginTime")
        wormRealTimeEntity.data?.beginTime = dataMap["begintime"].toString()
        wormRealTimeEntity.data?.moveWormGear = dataMap["movewormgear"].toString().toBoolean()
        wormRealTimeEntity.data?.dryingTemperatureReal = dataMap["dryingtemperaturereal"].toString().toFloat()
        wormRealTimeEntity.data?.wormFlap = dataMap["wormflap"].toString().toBoolean()
        wormRealTimeEntity.data?.vibrationDevice = dataMap["vibrationdevice"].toString().toBoolean()
        wormRealTimeEntity.data?.trapLamp = dataMap["traplamp"].toString().toBoolean()
        wormRealTimeEntity.data?.insecticidalTemperature = dataMap["insecticidaltemperature"].toString().toFloat()
        wormRealTimeEntity.data?.insecticidalTemperatureDifference =
            dataMap["insecticidaltemperaturedifference"].toString().toFloat()
        println("the runHour is :" + wormRealTimeEntity.data?.runHour)
        wormRealTimeRepository.save(wormRealTimeEntity)
//        if (ChronoUnit.MINUTES.between(this.compareTime, LocalDateTime.now()) > 60) {
//            wormRealTimeRepository.save(wormRealTimeEntity)
//            this.compareTime = LocalDateTime.now()
//        }
    }

    /**
     * 控制指令应答推送
     * @param
     * **/
    fun control(deviceAddr: String, type: String, data: List<HashMap<String, String>>) {
        TODO("处理数据")
    }

    /**
     * 接收getWormDeviceParams(deviceAddr: String)的设备应答数据推送
     * @param deviceAddr 设备地址
     * @param type 类型
     * @param data 列表形式的map
     * **/
    fun receive(deviceAddr: String, type: String, data: List<HashMap<String, String>>) {
        TODO("处理数据")
    }

    /**
     * 接收getWormDeviceParams(deviceAddr: String)的设备应答数据推送
     * @param deviceAddr 设备地址
     * @param type 类型
     * @param data 列表形式的map
     * **/
    fun transform(deviceAddr: String, type: String, data: List<HashMap<String, String>>) {
        TODO("处理数据")
    }

}
```