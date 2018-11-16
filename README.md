# Pomelo

## 專案啟動

### 啟動前：sh npm-install.sh

### 啟動game-server服務器：

`cd game-server` `>` `pomelo start`

### 啟動web-server服務器：

`cd web-server` `>` `node app.js`

## 啟動

```text
pomelo start [-e development | -e production] [--daemon]
```

**默认启动的是development模式，如果要启动正式环境，需要额外加一个production参数，--daemon指的是后台运行\(可直接下 -D\)**

## 停止

```text
pomelo stop
```

## pomelo-cli

### 安裝：

`npm install -g pomelo-cli`

### 登入：

`pomelo-cli -h host -P port -u username -p password`

* host&port是master server的,登入帳密設定於adminUser.json
* 預設登入指令： `pomelo-cli -h 127.0.0.1 -P 3005 -u monitor -p monitor`

## client端傳送訊息方式

#### notify：只傳送不接收

```text
this.pomelo.notify( 'wg.wgHandler.Echo' , {msg: msg} );
```

#### request：傳送並接收

```text
this.pomelo.request('wg.wgHandler.Echo', {
    msg: msg
} , function( data ) {
    console.log('get msg :' + data.code + '-' + data.msg);
});
```

## 日誌管理

### 日誌配置說明

* type： 指定appenders的类型，可以是console， dataFile， file 等，具体详见 log4js
* filename： 指定输出文件的路径
* pattern：指定输出日志的pattern
* maxLogSize：指定输出日志的最大大小
* layout：指定输出的layout样式
* backups：指定最大输出的文件数目
* category：指定该appender对应的category，如果没有该项，说明该appender是一个全局的appender
* replaceConsole：指定是否替换默认的console
* lineDebug：指定是否开启debug显示日志行数

### 日志等级从左到右依次提升：

TRACE, DEBUG, INFO, WARN, ERROR, FATAL

```text
{
  "appenders": [
    {
      "type": "console"
    },
    {
      "type": "file",
      "filename": "${opts:base}/../logs/gs/wg.log",
      "maxLogSize": 10485760,
      "layout": {
        "type": "pattern",
        "pattern": "[%d][%p][%c][%x{line}][%m][%n]",
        "tokens": {
          "line": "1233"
        }
      }
    ,"backups": 5,
      "category":"wg"
    }
  ],

  "levels": {
    "wg": "DEBUG"
  },

  "replaceConsole": true,

  "lineDebug": false
}
```

## Survey

### session設定參數

* uid : session.bind
* other : session.set `>` session.push\(**同步推至其餘server的session**\)

```text
// other
session.set("wg", "cluster-server-wg-0");
session.push( "wg" , function( err ) {

});
// uid
session.bind( uid , function( err ) {

});
```

### ChannelService

getChannel\(name,create\):當create參數=true時，如果channel不存在，便會create

