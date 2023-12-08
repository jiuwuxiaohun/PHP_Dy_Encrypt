---
title: 大牙加密 v1.0.0
language_tabs:
  - shell: Shell
  - http: HTTP
  - javascript: JavaScript
  - ruby: Ruby
  - python: Python
  - php: PHP
  - java: Java
  - go: Go
toc_footers: []
includes: []
search: true
code_clipboard: true
highlight_theme: darkula
headingLevel: 2
generator: "@tarslib/widdershins v4.0.17"


---


# 大牙加密


> v1.0.0


Base URLs:


* <a href="https://dyjm.ttmm.vip">正式环境: https://dyjm.ttmm.vip</a>


# 对外API接口




## POST 上传附件


POST /api/dy_encrypt/home/upload/file


> Body 请求参数


```yaml
file: file:///Users/haitian/Downloads/Adminlog.php
上传文件的key是file，值是文件内容，body类型是： multipart/form-data
```


### 请求参数


|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|x-api-key|header|string| 否 |none|
|body|body|object| 否 |none|
|» file|body|string(binary)| 是 |none|


> 返回示例


> 成功


```json
{
  "code": 0,
  "message": "success",
  "data": {
    "FileName": "Adminlog.php",
    "FilePath": "cuc8ijxaqie70qcput.php",
    "FileSize": 3361
  },
  "timestamp": 1690387941,
  "traceID": "b3443f77e0767517c68e8c4779863e01"
}
```


### 返回结果


|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|[hotgo.addons.dy_encrypt.api.UploadFileRes](#schemahotgo.addons.dy_encrypt.api.uploadfileres)|






## POST 执行加密


POST /api/dy_encrypt/home/encrypt/run


> Body 请求参数


```json
{
  "file_list": [
    {
      "file_name": "Adminlog.php",
      "file_path": "cuc8ijxaqie70qcput.php"
    }
  ],
  "presetting_type": 1,
  "custom_copyright": "自定义版权区域",
  "code_limit_date": "2024-07-27",
  "only_allow_server_ip": "127.0.0.1,192.168.1.1",
  "only_allow_bind_domain": "www.baidu.com,www.google.com,*.qq.com"
}
```


### 请求参数


|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|x-api-key|header|string| 否 |none|
|body|body|[hotgo.addons.dy_encrypt.api.EncryptRunReq](#schemahotgo.addons.dy_encrypt.api.encryptrunreq)| 否 |none|


> 返回示例


> 成功


```json
{
  "code": 0,
  "message": "success",
  "data": {
    "ok_number": 1,
    "err_number": 0,
    "file_list": [
      {
        "file_name": "Adminlog.php",
        "file_path": "cuc8ijxaqie70qcput.php",
        "uuid": "b351d5a7-4dac-45cf-b3d6-d107c882d574"
      }
    ]
  },
  "timestamp": 1690388020,
  "traceID": "fb1752e8f2767517ca8e8c47a8e791ba"
}
```


### 返回结果


|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|[hotgo.addons.dy_encrypt.api.EncryptRunRes](#schemahotgo.addons.dy_encrypt.api.encryptrunres)|






## GET 通过uuid下载加密附件


GET /api/dy_encrypt/home/down_encrypt_file_by_uuid


### 请求参数


|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|uuid|query|string| 是 |加密记录UUID|
|x-api-key|header|string| 否 |none|


> 返回示例


> 200 Response


```json
{}
```


### 返回结果


|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|[hotgo.addons.dy_encrypt.api.DownloadEncryptFileRes](#schemahotgo.addons.dy_encrypt.api.downloadencryptfileres)|




## GET 通过uuid读取加密附件


GET /api/dy_encrypt/home/get_encrypt_file_base64_by_uuid


### 请求参数


|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|uuid|query|string| 是 |加密记录UUID|
|x-api-key|header|string| 否 |none|


> 返回示例


> 成功


```json
{
  "code": 0,
  "message": "success",
  "data": {
    "file_name": "Adminlog.php",
    "file_size": 3361,
    "base64_code_str": "__________BASE64_CODE___________"
  },
  "timestamp": 1690388053,
  "traceID": "4a43986bfa767517cb8e8c47f79c456b"
}
```


### 返回结果


|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|[hotgo.addons.dy_encrypt.api.GetEncryptFileByUuidRes](#schemahotgo.addons.dy_encrypt.api.getencryptfilebyuuidres)|




# 数据模型


<h2 id="tocS_hotgo.addons.dy_encrypt.api.UploadFileRes">hotgo.addons.dy_encrypt.api.UploadFileRes</h2>


<a id="schemahotgo.addons.dy_encrypt.api.uploadfileres"></a>
<a id="schema_hotgo.addons.dy_encrypt.api.UploadFileRes"></a>
<a id="tocShotgo.addons.dy_encrypt.api.uploadfileres"></a>
<a id="tocshotgo.addons.dy_encrypt.api.uploadfileres"></a>


```json
{
  "FileName": "string",
  "FilePath": "string",
  "FileSize": 0
}


```


### 属性


|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|FileName|string(string)|false|none||none|
|FilePath|string(string)|false|none||none|
|FileSize|integer(int64)|false|none||none|


<h2 id="tocS_hotgo.addons.dy_encrypt.api.UploadFileReq">hotgo.addons.dy_encrypt.api.UploadFileReq</h2>


<a id="schemahotgo.addons.dy_encrypt.api.uploadfilereq"></a>
<a id="schema_hotgo.addons.dy_encrypt.api.UploadFileReq"></a>
<a id="tocShotgo.addons.dy_encrypt.api.uploadfilereq"></a>
<a id="tocshotgo.addons.dy_encrypt.api.uploadfilereq"></a>


```json
{
  "File": {}
}


```


### 属性


|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|File|[github.com.gogf.gf.v2.net.ghttp.UploadFile](#schemagithub.com.gogf.gf.v2.net.ghttp.uploadfile)|false|none||none|


<h2 id="tocS_github.com.gogf.gf.v2.net.ghttp.UploadFile">github.com.gogf.gf.v2.net.ghttp.UploadFile</h2>


<a id="schemagithub.com.gogf.gf.v2.net.ghttp.uploadfile"></a>
<a id="schema_github.com.gogf.gf.v2.net.ghttp.UploadFile"></a>
<a id="tocSgithub.com.gogf.gf.v2.net.ghttp.uploadfile"></a>
<a id="tocsgithub.com.gogf.gf.v2.net.ghttp.uploadfile"></a>


```json
{}


```


### 属性


*None*


<h2 id="tocS_hotgo.addons.dy_encrypt.api.GetEncryptFileByUuidRes">hotgo.addons.dy_encrypt.api.GetEncryptFileByUuidRes</h2>


<a id="schemahotgo.addons.dy_encrypt.api.getencryptfilebyuuidres"></a>
<a id="schema_hotgo.addons.dy_encrypt.api.GetEncryptFileByUuidRes"></a>
<a id="tocShotgo.addons.dy_encrypt.api.getencryptfilebyuuidres"></a>
<a id="tocshotgo.addons.dy_encrypt.api.getencryptfilebyuuidres"></a>


```json
{
  "file_name": "string",
  "file_size": 0,
  "base64_code_str": "string"
}


```


### 属性


|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|file_name|string(string)|false|none||加密文件名称|
|file_size|integer(int)|false|none||加密文件大小|
|base64_code_str|string(string)|false|none||加密后源码BASE64编码|


<h2 id="tocS_hotgo.addons.dy_encrypt.api.EncryptRunRes">hotgo.addons.dy_encrypt.api.EncryptRunRes</h2>


<a id="schemahotgo.addons.dy_encrypt.api.encryptrunres"></a>
<a id="schema_hotgo.addons.dy_encrypt.api.EncryptRunRes"></a>
<a id="tocShotgo.addons.dy_encrypt.api.encryptrunres"></a>
<a id="tocshotgo.addons.dy_encrypt.api.encryptrunres"></a>


```json
{
  "ok_number": 0,
  "err_number": 0,
  "file_list": [
    {
      "file_name": "string",
      "file_path": "string",
      "uuid": "string"
    }
  ]
}


```


### 属性


|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|ok_number|integer(int)|false|none||成功的数量|
|err_number|integer(int)|false|none||失败的数量|
|file_list|[[hotgo.addons.dy_encrypt.api.FileListLog](#schemahotgo.addons.dy_encrypt.api.filelistlog)]|false|none||待加密文件列表(数组)|


<h2 id="tocS_hotgo.addons.dy_encrypt.api.FileListLog">hotgo.addons.dy_encrypt.api.FileListLog</h2>


<a id="schemahotgo.addons.dy_encrypt.api.filelistlog"></a>
<a id="schema_hotgo.addons.dy_encrypt.api.FileListLog"></a>
<a id="tocShotgo.addons.dy_encrypt.api.filelistlog"></a>
<a id="tocshotgo.addons.dy_encrypt.api.filelistlog"></a>


```json
{
  "file_name": "string",
  "file_path": "string",
  "uuid": "string"
}


```


### 属性


|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|file_name|string(string)|false|none||待加密文件名|
|file_path|string(string)|false|none||待加密文件路径|
|uuid|string(string)|false|none||加密记录的UUID|


<h2 id="tocS_hotgo.addons.dy_encrypt.api.EncryptRunReq">hotgo.addons.dy_encrypt.api.EncryptRunReq</h2>


<a id="schemahotgo.addons.dy_encrypt.api.encryptrunreq"></a>
<a id="schema_hotgo.addons.dy_encrypt.api.EncryptRunReq"></a>
<a id="tocShotgo.addons.dy_encrypt.api.encryptrunreq"></a>
<a id="tocshotgo.addons.dy_encrypt.api.encryptrunreq"></a>


```json
{
  "file_list": [
    {
      "file_name": "string",
      "file_path": "string"
    }
  ],
  "presetting_type": 1,
  "code_limit_date": "string",
  "only_allow_bind_domain": "string",
  "only_allow_server_ip": "string",
  "custom_copyright": "string",
  "is_share_vm": true,
  "is_insert_logic_snag": true,
  "is_mix_string": true,
  "is_mix_const": true,
  "is_mix_var": true,
  "is_mix_control": true,
  "is_anti_debug": true,
  "is_rubbish_code": true,
  "is_big_loop_optimize": true
}


```


### 属性


|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|file_list|[[hotgo.addons.dy_encrypt.api.FileList](#schemahotgo.addons.dy_encrypt.api.filelist)]|true|none||待加密文件列表(数组)|
|presetting_type|integer(int)|true|none||预设配置类型 1:推荐配置 2:最大保护 3:最佳性能 95:自定义配置|
|code_limit_date|string(*gtime.Time)|false|none||代码限制运行时间|
|only_allow_bind_domain|string(string)|false|none||限制绑定域名|
|only_allow_server_ip|string(string)|false|none||限制服务器IP|
|custom_copyright|string(string)|false|none||自定义版权信息|
|is_share_vm|boolean(bool)|false|none||启动虚拟机共享|
|is_insert_logic_snag|boolean(bool)|false|none||启动逻辑暗桩|
|is_mix_string|boolean(bool)|false|none||启用字符串混淆|
|is_mix_const|boolean(bool)|false|none||启用常量池混淆|
|is_mix_var|boolean(bool)|false|none||启用变量名混淆|
|is_mix_control|boolean(bool)|false|none||启用控制流打乱|
|is_anti_debug|boolean(bool)|false|none||启用反调试|
|is_rubbish_code|boolean(bool)|false|none||启用垃圾代码|
|is_big_loop_optimize|boolean(bool)|false|none||启动大循环优化|


<h2 id="tocS_hotgo.addons.dy_encrypt.api.FileList">hotgo.addons.dy_encrypt.api.FileList</h2>


<a id="schemahotgo.addons.dy_encrypt.api.filelist"></a>
<a id="schema_hotgo.addons.dy_encrypt.api.FileList"></a>
<a id="tocShotgo.addons.dy_encrypt.api.filelist"></a>
<a id="tocshotgo.addons.dy_encrypt.api.filelist"></a>


```json
{
  "file_name": "string",
  "file_path": "string"
}


```


### 属性


|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|file_name|string(string)|true|none||待加密文件名|
|file_path|string(string)|true|none||待加密文件路径|


<h2 id="tocS_hotgo.addons.dy_encrypt.api.DownloadEncryptFileRes">hotgo.addons.dy_encrypt.api.DownloadEncryptFileRes</h2>


<a id="schemahotgo.addons.dy_encrypt.api.downloadencryptfileres"></a>
<a id="schema_hotgo.addons.dy_encrypt.api.DownloadEncryptFileRes"></a>
<a id="tocShotgo.addons.dy_encrypt.api.downloadencryptfileres"></a>
<a id="tocshotgo.addons.dy_encrypt.api.downloadencryptfileres"></a>


```json
{}


```


### 属性


*None*




