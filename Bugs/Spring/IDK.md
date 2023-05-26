```kotlin
        /**
         * 根据协议中byte[4]为施肥机设置状态
         * **/
        private fun byteFourSetStates(state: String, fer: Fertilizer) {
            for (i in 0 until 8) {
                when (i) {
                    0 -> fer.valveEight = state[i] == '1'
                    1 -> fer.valveSeven = state[i] == '1'
                    2 -> fer.valveSix = state[i] == '1'
                    3 -> fer.valveFive = state[i] == '1'
                    4 -> fer.valveFour = state[i] == '1'
                    5 -> fer.valveThree = state[i] == '1'
                    6 -> fer.valveTwo = state[i] == '1'
                    7 -> fer.valveOne = state[i] == '1'
                    else -> continue
                }
            }
        }

        /**
         * 根据协议中byte[5]为施肥机设置状态
         * **/
        private fun byteFiveSetStates(state: String, fer: Fertilizer) {
            for (i in 0 until 8) {
                when (i) {
                    0 -> fer.fatC = state[i] == '1'
                    1 -> fer.fatB = state[i] == '1'
                    2 -> fer.fatA = state[i] == '1'
                    3 -> fer.fatMixC = state[i] == '1'
                    4 -> fer.fatMixB = state[i] == '1'
                    5 -> fer.fatMixA = state[i] == '1'
                    6 -> fer.fatPump = state[i] == '1'
                    7 -> fer.waterPump = state[i] == '1'
                    else -> continue
                }
            }
        }

        /**
         * 根据协议中byte[7]为施肥机设置状态
         * **/
        private fun byteSevenSetStates(state: String, fer: Fertilizer) {
            for (i in 0 until 8) {
                when (i) {
                    4 -> fer.wheelControl = state[i] == '1'
                    5 -> fer.remote = state[i] == '1'
                    6 -> fer.auto = state[i] == '1' //true是手动 false是自动
                    7 -> fer.wheelOrTiming = state[i] == '1'
                    else -> continue
                }
            }
        }
```