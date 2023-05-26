```kotlin
    private fun ensureState(byteArray: ByteArray?, fer: Fertilizer) {
            val data = IntArray(FERTILIZER_DATA_LENGTH)
            //取出每一个字节数组 按照对应规则读取信息
            for (i in 0 until FERTILIZER_DATA_LENGTH) {
                //2位16进制，最大值为255，但是byte中最大值为127 byte中由于符号位的存在127后是-128
                if (byteArray!![i] < 0) {
                    data[i] += byteArray[i].toString().toInt() + 256
                } else {
                    data[i] = byteArray[i].toString().toInt()
                }
                //转为二进制字符串
                val state = ToBinaryString.toUnsignedBinaryString(data[i], 8)
                when (i) {
                    0 -> fer.address = data[i].toString()
                    4 -> byteFourSetStates(state, fer)
                    5 -> byteFiveSetStates(state, fer)
                    7 -> byteSevenSetStates(state, fer)
                    else -> continue
                }
            }
            val fertilizer = fertilizerRepository.findByAddress(fer.address)
            if (fertilizer != null) {
                fer.id = fertilizer.id
                fertilizerRepository.save(fer)
            } else {
                fertilizerRepository.save(fer)
            }
            println("done")
        }
        
```