```mysql

Data Source: 47 Schema: dbformal Table: testcq  
-- auto-generated definition
create table testcq
(
    id                  bigint auto_increment
        primary key,
    deviceKey           varchar(100)  null,
    insecticidalTem     varchar(100)  null,
    dryingTem           varchar(100)  null,
    batteryLevel        varchar(100)  null,
    rainfallStatus      varchar(100)  null,
    illuminance         varchar(100)  null,
    operationMode       varchar(200)  null,
    lightTrap           varchar(100)  null,
    insectRainBaffle    varchar(100)  null,
    insecticidalBaffle  varchar(100)  null,
    dryingBaffle        varchar(100)  null,
    migrationDevice     varchar(100)  null,
    vibrationDevice     varchar(100)  null,
    fillLight           varchar(100)  null,
    insecticidalControl varchar(100)  null,
    dryingControl       varchar(100)  null,
    camear              varchar(100)  null,
    createTime          varchar(200)  null,
    analyzePictureUrl   varchar(500)  null,
    analyseData         varchar(4000) null,
    analyzeTime         varchar(200)  null
)
    row_format = DYNAMIC;

create index deviceKey
    on testcq (deviceKey);
 Show table preview 
```