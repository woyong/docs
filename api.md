#松鼠相册API http://api.songshuyun.com

##帐号

* 用户获取手机验证码 

*请求语法*

    POST /mobile/authorization

*请求参数*

| 参数名 | 类型 | 描述 |  
| ----- | ----------------- | ------------------- |  
|  pnumber | string | **required.** 用户手机号码 |  

* 用户根据手机验证码进行验证

*请求语法*

    PUT /mobile/authorization

*请求参数*

| 参数名 | 类型 | 描述 |  
| ----- | ----------------- | ------------------- |  
| pnumber | string | **required.** 用户手机号码 |  
| vcode | string | **required.** 短信验证码 |  


* 手机注册帐号

*请求语法*

    POST /accounts/mobile

*请求参数*

| 参数名 | 类型 | 描述 |  
| ----- | ----------------- | ------------------- |  
| pnumber | string | **required.** 用户手机号码 |  
| vcode | string | **required.** 短信验证码 |  
| passwd | string | **required.** 帐号密码 |  

* 邮箱获取注册验证码

*请求语法*

    POST /email/confirmation

*请求参数*

| 参数名 | 类型 | 描述 |  
| ----- | ----------------- | ------------------- |  
|  email | string | **required.** email邮箱 |  

* 用户根据验证码进行邮箱验证

*请求语法*

    PUT /email/confirmation

*请求参数*

| 参数名 | 类型 | 描述 |  
| ----- | ----------------- | ------------------- |  
|  email | string | **required.** email邮箱 |  
|  vcode | string | **required.** 邮箱验证码 |  

* 用户使用已验证邮箱注册帐号

*请求语法*

    POST /accounts/email

*请求参数*

| 参数名 | 类型 | 描述 |  
| ----- | ----------------- | ------------------- |  
| email | string | **required.** email邮箱 |  
| vcode | string | **required.** 邮箱验证码 |  
| passwd | string | **required.** 帐号密码 |  


## 用户信息
* 用户登录

*请求语法*

    GET /user
    Authorization: Bearer <Token>

* 修改用户信息

*请求语法*

    PUT /user
    Authorization: Bearer <Token>

*请求参数*

| 参数名 | 类型 | 描述 |  
| ----- | ----------------- | ------------------- |  
| nickname | string | 用户昵称 |  
| avatar | file | 用户头像 |  

* 用户帐号绑定baidu推送channel

*请求语法*

    POST /baidu/push
    Authorization: Bearer <Token>

*请求参数*

| 参数名 | 类型 | 描述 |  
| ----- | ----------------- | ------------------- |  
| user_id | string | **required.** 百度推送应用端'user_id'字段 |  
| channel_id | string | **required.** 百度推送应用端'channel_id'字段 |  
| pkg | string | **required** 应用包名 |  

## 用户绑定设备
* 用户申请绑定设备

*请求语法*

    POST /user/device/<sn>/binding
    Authorization: Bearer <Token>

*请求参数*

| 参数名 | 类型 | 描述 |  
| ----- | ----------------- | ------------------- |  
| sn | string | **required.** 设备序列号 |  

## 用户联系人
* 用户添加联系人

*请求语法*

    POST /user/contact/<contact>
    Authorization: Bearer <Token>

*请求参数*

| 参数名 | 类型 | 描述 |  
| ----- | ----------------- | ------------------- |  
| username | string | **required.** 申请人/设备用户名 |  
| contact | string | **required.** 联系人用户名 |  

* 用户获取联系人列表

*请求语法*

    GET /user/contact
    Authorization: Bearer <Token>

*请求参数*

| 参数名 | 类型 | 描述 |  
| ----- | ----------------- | ------------------- |  
| username | string | 申请人/设备用户名 |  

* 用户删除联系人

*请求语法*

    DELETE /user/contact/<contact>
    Authorization: Bearer <Token>

*请求参数*

| 参数名 | 类型 | 描述 |  
| ----- | ----------------- | ------------------- |  
| username | string | 申请人/设备用户名 |  
| contact | string | **required.** 联系人用户名 |  

## Moment
* 获取qiniu上传token.

*请求语法*

    GET /qiniu/uptoken
    Authorization: Bearer <Token>

* 发布moment(图片)

*请求语法*

    POST /user/moment/pic
    Authorization: Bearer <Token>

*请求参数*

| 参数名 | 类型 | 描述 |  
| ----- | ----------------- | ------------------- |  
| devices | string | 设备集合, 多个设备sn以','隔开 |  
| desc | string | moment描述 |  
| photo | string | **required.** moment图片key集合, 多个key以','隔开|  
| audio | string | moment 语音描述, 目前只支持一个 |  

* 发布moment(视频)

*请求语法*

    POST /user/moment/video
    Authorization: Bearer <Token>

*请求参数*

| 参数名 | 类型 | 描述 |  
| ----- | ----------------- | ------------------- |  
| devices | string | 设备集合, 多个设备sn以','隔开 |  
| video | string | **required.** 视频key |  

## 设备
* 设备激活

*请求语法*

    POST /device

*请求参数*

| 参数名 | 类型 | 描述 |  
| ----- | ----------------- | ------------------- |  
| sn | string | **required.** 设备序列号 |  
| imei | string | **required.** 设备IMEI号 |  
| mac | string | **required.** 设备MAC地址 |  


### OAuth2
* 验权获取Token.

*请求语法*

    POST /oauth2/access_token

*请求参数*

| 参数名 | 类型 | 描述 |  
| ----- | ----------------- | ------------------- |  
| client_id | string | **required.** 客户端id |  
| client_secret | string | **required.** 客户端secret |  
| grant_type | string | **required.** password |  
| username | string | **required.** 用户名 |  
| passwork | string | **required.** 密码 |  

---
说明: client_id=1c9ffe11bcd58be38daf & client_secret=dc45f8768c4e8bd795562a92481d79013a96aa1d


#附注
[^host]: http://api.songshuyun.com