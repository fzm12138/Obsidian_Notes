```xml
<if test="startTime != null and startTime != ''">
          xxxxxxx  
 </if>
```
**会报错
invalid comparison: java.util.Date and java.lang.String(无效的比较)**
- 问题出在
```mysql
and startTime !=''
```
因为不能用date与string比较
比较日期的时候直接比较即可
