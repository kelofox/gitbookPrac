## TypeScript

#### 類型斷言語法：

* <類型>值

* 值 as 類型

#### import：

* 複數import：``` import {BonusType, RoomState} from "../../AirEnum"; ```

* 別名： ``` import {AirServerSetting as setting} from "../../AirServerSetting"; ```

## WebStorm

### Hot Key：

指令					  |功能
----------------------|:--------------------------:
command + shift + f   |全專案搜索
command + b 			  |至有呼叫該function的行數
双击shift           	  |弹出小浮窗搜索所有
command+shift+U 		  |大小写转换
command+shift+加号/减号|收缩整个文档的代码块
shift+F6              |重命名

### 設定：

#### 橫向拖曳時會自動捲動：
Settings `>` Editor `>` General, Virtual Space `>` Show virtual space at file bottom

## Javascript

#### assert(check,errorMsg)

assert方法接受两个参数，当第一个参数对应的布尔值为true时，不会有任何提示，返回undefined。当第一个参数对应的布尔值为false时，会抛出一个错误(AssertionError)，该错误的提示信息就是第二个参数设定的字符串。

```
var assert = require("assert");
assert(false , "assert測試");	//	throw AssertionError,error message = assert測試
```

#### json

* json `>` object : ``` var obj = JSON.parse(text); ```

* object `>` json : ``` var text = JSON.stringify(obj); ```

#### console log add color

* 規則：字串前端加顏色代碼，尾端加Rest代碼(``` \x1b[0m ```)

* 效果代碼加於顏色代碼前面，非必須

* EX:``` console.log("\x1b[1m\x1b[34monRecv_1 : [%s]下注成功(資產:%s)\x1b[0m", currentTime() , msg.b ); ```

##### 效果代碼

Name        |Code         		  |Effect
:----------:|:-----------------:|:-----:
Bright      |``` \x1b[1m ```    |加粗
Dim         |``` \x1b[2m ```    |暗色
Underscore  |``` \x1b[4m ```    |加底線
Blink       |``` \x1b[5m ```    |???
Reverse     |``` \x1b[7m ```    |加背景色
Hidden      |``` \x1b[8m ```    |???

##### 顏色代碼

Name         |Code         	  |Effect
:-----------:|:----------------:|:-----:
FgBlack      |``` \x1b[30m ```  |黑
FgRed        |``` \x1b[31m ```  |紅
FgGreen      |``` \x1b[32m ```  |綠
FgYellow     |``` \x1b[33m ```  |黃
FgBlue       |``` \x1b[34m ```  |藍
FgMagenta    |``` \x1b[35m ```  |紫
FgCyan       |``` \x1b[36m ```  |青
FgWhite      |``` \x1b[37m ```  |白

##### 填滿代碼

Name         |Code              |Effect
:-----------:|:----------------:|:-----:
BgBlack      |``` \x1b[40m ```  |黑(填滿)
BgRed        |``` \x1b[41m ```  |紅(填滿)
BgGreen      |``` \x1b[42m ```  |綠(填滿)
BgYellow     |``` \x1b[43m ```  |黃(填滿)
BgBlue       |``` \x1b[44m ```  |藍(填滿)
BgMagenta    |``` \x1b[45m ```  |紫(填滿)
BgCyan       |``` \x1b[46m ```  |青(填滿)
BgWhite      |``` \x1b[47m ```  |白(填滿)
