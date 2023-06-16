数据库版本导致的编码格式不识别
8.0 --->> 5.7
- replace“**utf8mb4_0900_ai_ci**” with “**utf8mb4_general_ci**” and “**CHARSET=utf8mb4**” with “**CHARSET=utf8**“.
- COLLATION 'utf8mb4_general_ci' is not valid for CHARACTER SET 'utf8'
	- replace `CHARSET=utf8`  为 `CHARSET=utf8mb4`


