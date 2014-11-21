## 获取timeline

    GET /user/moment

```python
{
    "id": 1545, #moment id
    "created": 1416534270, # 发布时间
    "albums": [ ], # 目前没有实际意义
    "author": { # moment发布者的信息
        "username": "18513509728", # 用户名
        "display_name": "小星星小松鼠", # 用户昵称
        "avatar": "", # 用户头像
        "voip": { # 此信息在timeline中可忽略
            "voippwd": "",
            "subaccount": "",
            "voip": "83252200000013",
            "subtoken": ""
        },
        "is_device": false # 判断用户是否是设备
    },
    "media": [
        {   # 一个meida就代表单一的audio/photo/video, 为了方便，写在一起.
            "id": 2692,
            "type": 2, # media 类型 (0:代表照片,1:代表音频,2:代表视频)
            "status": 0, # 存储状态 (0:代表正常, 404:代表已删除)
            "size": 1360938, #文件大小
            "photo": {
                "id": 2520,
                "width": 3120, # 照片的实际宽度
                "height": 4208, # 照片的实际高度
                "timestamp": "", # 照片的拍摄时间
                "src": "", # 无效
                "small_thumb": "", # 无效
                "thumb": "", # 无效
                "qiniu_origin": "", # 照片的原始文件地址
                "qiniu_small_thumb": "", # 照片256x256缩略图地址
                "qiniu_thumb": "" # 照片512x512缩略图地址
            },
            "audio":  {
                "id": 111,
                "src": "", # 音频请求url
                "duration": 7.72375 # 音频时长
            },
            "video": {
                "id": 53,
                "src": "", # 视频请求url
                "duration": 21.78 #视频时长
            }
        }
    ],
    "description": "", # moment 描述
    "reviews": [
        {
            "id": 537,
            "user": { # 用户信息(请参照发布者信息)
                "username": "18513509728",
                "display_name": "小星星小松鼠",
                "avatar": "http://ss-gallery.qiniudn.com/fe640cb5c82bc4e8259ad12f3fc5129a?e=1416541138&token=tLAJGAcAg9qyYO9eE4uD1iqanrdlqhXUUCw-hwS-:a8lRm4m61fxzlsIaikYzFzbwln8=",
                "voip": {
                    "voippwd": "",
                    "subaccount": "",
                    "voip": "83252200000013",
                    "subtoken": ""
                },
            "is_device": false
            },
            "body": "uuuuuuuuuuuu", # 评论内容
            "reply_to": "", # 暂时无效
            "created": 1416534531 # 评论时间
        }
    ],
    "like": [
        { # 用户信息(请参考发布者信息)
            "username": "18513509728",
            "display_name": "小星星小松鼠",
            "avatar": "http://ss-gallery.qiniudn.com/fe640cb5c82bc4e8259ad12f3fc5129a?e=1416541138&token=tLAJGAcAg9qyYO9eE4uD1iqanrdlqhXUUCw-hwS-:a8lRm4m61fxzlsIaikYzFzbwln8=",
            "voip": {
                "voippwd": "",
                "subaccount": "",
                "voip": "83252200000013",
                "subtoken": ""
            },
            "is_device": false
        }
    ],
    "devices": [
        { # 设备也是一个用户(请参考用户信息)
            "username": "MIPAD",
            "display_name": "MIPAD",
            "is_device": true,
            "is_binding": false,
            "avatar": "",
            "voip": {
                "voippwd": "",
                "subaccount": "",
                "voip": "83252200000025",
                "subtoken": ""
            },
            "media_number": 161 #设备收到的media数量.
        }
    ]
}
```