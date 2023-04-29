**建模软件以及作用**
-   3DMax（格式转换+场景整合+Datasmith导出）
-   Maya（模型骨骼动画）
-   Blender(天下第一）
-   SketchUp（面数低）
-   Revit（1:1参数化建模）
-   Rhino（高精度地形）
-   倾斜摄影OSGB数据（作为外围环境模型）
-   Marvelous Designer(布料解算）
-   Daz studio(人体表现）
-   CityEngine CGA规则（低模城市集群快速生成）
-   PointCloud点云数据（作为大远景背景）
-   Houdini（程序化建模）
-   Bentley（实景建模）
----
**地形插件**
-   Landscap根据灰度图生成地形（灰度图来源：国家地质信息网，美国国家地质网)
-   手工勾勒雕刻山脉+三位模型堆砌地形环境（模型来自UE4商城地形素材）
-   CAD图纸结合WorldMap生成可视化地形
-   WorldCreator2结合灰度图模拟真实地形（效果最好）
-   WorldMachine结合DEM数据生成灰度图
-   根据生成模型手工二次拓扑制作地形（效果好，性能优）
----
**道路**
-   手工建模：适用于定制化崎岖不规则道路
-   模块化程序道路：适用于井字整齐排列道路（参考商城资源：Roads Generator Pack)
-   Landscape样条线道路：适用于山脉之字形道路(参考商城资源：Brushify Country Roads Pack）
-   GIS矢量数据生成道路：适用于城市级高密度复杂道路（参考CityEngine）
---- 
## **水**

**基于UE4 4.26水系统**

-   湖泊，河流，海洋，池塘，瀑布素材库积累，结合船只，码头等配景。
-   物理水粒子（eg：喷泉、消防模拟..等）
-   进阶模拟可以参考Asher的SPH水粒子方案。
-----
**物联网数据采集**
1.  **获取数据**：数据包括但不限于：点、线、面（格式通常为Json/GeoJson以及CSV、Shp等）同时可以支持MySQL, SQL Server,Oracle, Hive, PostgreSQL, 等数据库。
2.  **读取数据**：可以通过LowEntryHttpRequest、LowEntryJson插件读取中台数据。
3.  **处理数据**：通常数据都是按照经纬坐标集成的，这里我们需要将经纬坐标转为引擎坐标，推荐插件（[SimulationPlugin](https://link.zhihu.com/?target=http%3A//mp.weixin.qq.com/s%3F__biz%3DMzU4OTY5OTM1Ng%3D%3D%26mid%3D2247485012%26idx%3D1%26sn%3Dd1edaa5d9d36c8117addceca61193de5%26chksm%3Dfdc8c627cabf4f31165168a06f08018b94879a56c8d66adde4b83a332f931bd12f6c159ae371%26scene%3D21%23wechat_redirect)），4.27已内置。然后进一步解析其它需要的参数即可。
4.  **应用数据**：将数据转化为可视的效果，例如：当地停车场位置以及内部信息。  
    *常见数据驱动效果有：热力图、OD线（[UE4数字孪生 OD线](https://link.zhihu.com/?target=http%3A//mp.weixin.qq.com/s%3F__biz%3DMzU4OTY5OTM1Ng%3D%3D%26mid%3D2247490948%26idx%3D1%26sn%3Ddf5c0e0d90a7e99ce1fabdae5058c646%26chksm%3Dfdc8ddf7cabf54e12fe4d882ef9c818f2db49176e7877d1a4eaab0d23938925ce9ebb0ad5887%26scene%3D21%23wechat_redirect)）、标签POI、路网。
-----


前后端：
- Vue
- React
- Angular