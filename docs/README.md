# 简介
    
来源于[NeteaseCloudMusicApi]()

# 功能特征

1.登录  
2.刷新登录  
3.获取用户信息 , 歌单，收藏，mv, dj 数量  
4.获取用户歌单  
5.获取用户电台  
6.获取用户关注列表  
7.获取用户粉丝列表  
8.获取用户动态  
9.获取用户播放记录  
10.获取精品歌单  
11.获取歌单详情  
12.搜索  
13.搜索建议  
14.获取歌词  
15歌曲评论  
16.收藏单曲到歌单  
17.专辑评论  
18.歌单评论  
19.mv 评论  
20.电台节目评论  
21.banner  
22.获取歌曲详情  
23.获取专辑内容  
24.获取歌手单曲  
25.获取歌手 mv  
26.获取歌手专辑  
27.获取歌手描述  
28.获取相似歌手  
29.获取相似歌单  
30.相似 mv  
31.获取相似音乐  
32.获取最近 5 个听了这首歌的用户  
33.获取每日推荐歌单  
34.获取每日推荐歌曲  
35.私人 FM  
36.签到  
37.喜欢音乐  
38.垃圾桶  
39.歌单 ( 网友精选碟 )  
40.新碟上架  
41.热门歌手  
42.最新 mv  
43.推荐 mv  
44.推荐歌单  
45.推荐新音乐  
46.推荐电台  
47.推荐节目  
48.独家放送  
49.mv 排行  
50.获取 mv 数据  
51.播放 mv/视频  
52.排行榜  
53.歌手榜  
54.云盘  
55.电台 - 推荐  
56.电台 - 分类  
57.电台 - 分类推荐  
58.电台 - 订阅  
59.电台 - 详情  
60.电台 - 节目  
61.给评论点赞  
62.获取动态  
63.获取热搜  
64.发送私信  
65.发送私信歌单  
66.新建歌单  
67.收藏/取消收藏歌单  
68.歌单分类  
69.收藏的歌手列表  
70.订阅的电台列表  
71.相关歌单推荐  
72.付费精选接口  
73.音乐是否可用检查接口  
74.登录状态  
75.获取视频数据  
76.发送/删除评论  
77.热门评论  
78.视频评论  
79.退出登录  
80.所有榜单  
81.所有榜单内容摘要  
82.收藏视频  
83.收藏 MV  
84.视频详情  
85.相关视频  
86.关注用户  
87.新歌速递  
88喜欢音乐列表(无序)  


# 接口文档

#### 登录

- 1.手机登录

**必选参数：** `phone：`手机号  `password：`密码  
**接口地址：** `/login/cellphone`  
**调用示例：** `/login?/cellphone?phone=xxx&password=xxx`


- 2.邮箱登录  

**必选参数：**  `email: `163邮箱 `password:` 密码   
**接口地址：**  `/login`  
**调用示例：**  `login?email=xxx&password=xxx`
!> 完成登录后，浏览记录会保存在cookies中用于登录  

#### 刷新登录  
说明：调用此接口，可刷新登录状态  

**调用示例：** `/login/redresh` 

#### 退出登录  
说明：调用此接口，可退出登录 

**调用示例：** `/logout`  

#### 登录状态  
说明：调用此接口，可获取登录状态 

**接口地址：**  `/login/status`   

#### 获取用户详情  
说明：调用此接口，可获取用户状态  

**必选参数：** `uid:` 用户id  
**接口地址：** `/user/detail`  
**调用示例：**  `/user/detail?uid=1111`    

#### 获取用户信息、歌单、收藏、mv、dj数量  
说明：调用此接口，可以获取用户信息  

**接口地址：** `/user/subcount`  
**调用示例：** `/user/subcount`  

#### 更新用户信息  
说明：登陆后调用此接口，传入相关信息，可以更新用户信息

**必选参数：**  
```
    gender: 性别 0: 保密 1:男 2:女  

    birthday: 出生日期，时间戳 nuix timestamp  

    nickname: 用户昵称  

    province: 省份id  

    city: 城市id  

    signature: 用户签名  
```
**接口地址：** `/user/subcount`  
**调用示例：** `/user/update/?gender=0&signature=测试签名&city=440300&nickname=binary&birthday=1525918298004&province=440000`

#### 获取用户歌单
说明：登陆后调用此接口，传入用户id，可以获取用户歌单  

**必选参数：**  `uid:` 用户id  
**接口地址：**  `/user/playlist`  
**调用示例：**  `/user/playlist?uid=32953014`  

#### 更新歌单  
说明：登陆后调用此接口，可以更新用户歌单   

**参数：**
```
    id: 歌单id  

    name: 歌曲名称  

    desc: 歌单描述  

    tags: 歌单tag

```  
**接口地址：** `/playlist/update`  
**调用示例：** `/playlist/update/?id=24381616&name=新歌单&desc=描述&tags=学习`  

#### 发送私信  
说明：登陆后调用此接口 , 传入用户 id 和要发送的信息, 可以发送私信,返回内容为历史私信,包含带歌单的私信信息(注:不能发送私信给自己)  

**必选参数：** 
```
    user_ids: 用户id，多个需要用逗号隔开  

    msg: 要发送的消息  
```
**接口地址：** `/send/text`  
**调用示例：** `/send/text?user_ids=32953014&msg=test`,`/send/text?user_ids=32953014,475625142&msg=test`  

#### 发送私信（带歌单） 
说明： 登陆成功后调用此接口，传入用户id和要发送的信息和歌单id，可以发带个歌单的私信（但不能重复） 

**必选参数：** 
```
    user_ids: 用户id，可以多个、需逗号隔开  

    msg: 要发送的消息  
```
**接口地址：**  `/send/playlist`  
**调用示例：**  `/send/playlist?msg=test&user_ids=475625142&playlist=705123491,/send/playlist?msg=test2&user_ids=475625142,32953014&playlist=705123493`  


#### 获取用户电台  
说明：登陆后调用此接口，传入用户id，可以获取用户电台

**必须参数：** `uid：` 用户id  
**接口地址：** `/user/dj`  
**调用示例：** `/user/dj?uid=32953014`  

#### 获取用户关注列表  
说明： 登陆成功后调用此接口，传入用户id，可以获取用户关注列表  

**必选参数：** `uid:` 用户id  
**可选参数：** 
```
    limit: 返回数量，默认为0  

    offset: 偏移数量，用于分页 如 :( 页数 -1)*30, 其中 30 为 limit 的值 , 默认为 0
```
**接口地址：** `/user/follows`  
**调用示例：** `/user/follows?uid=32953014`  

#### 获取用户播放记录  
说明：登陆后调用此接口，传入用户id，可获取播放记录  

**必传参数：** `uid:` 用户id  
**可选参数：** `type:` type=1 时只返回 weekData, type=0 时返回 allData  
**接口地址：** `/user/record`  
**调用示例：** `/user/record?uid=32953014&type=1`  

#### 获取动态消息  
说明： 调用此接口，可以获得各种动态，对应网页版网易云，朋友界面里的各种动态消息 ，如分享的视频，音乐，照片等！  

**必须参数：** `未知`  
**接口地址：** `/event`  
**调用示例：** `/event`  

#### 歌手分类列表  
说明：调用此接口,可获取歌手分类列表 必选参数 : cat : 即 category Code,歌手类型,默认 1001,返回华语男歌手数据  

**可选参数：** 
```
    limit: 返回数量、默认为30页  

    offset: 偏移量、用于分页  如 :( 页数 -1)*30, 其中 30 为 limit 的值 , 默认为 0  

    initial: 按首字母索引查找参数,如 `/artist/list?cat=1001&initial=b` 返回内容将以 name 字段开头为 b 或者拼音开头为 b 为顺序排列  
```
category Code 取值:  

```
ategory Code 取值:

入驻歌手 5001  

华语男歌手 1001  

华语女歌手 1002  

华语组合/乐队 1003  

欧美男歌手 2001  

欧美女歌手 2002  

欧美组合/乐队 2003  

日本男歌手 6001  

日本女歌手 6002  

日本组合/乐队 6003  

韩国男歌手 7001  

韩国女歌手 7002  

韩国组合/乐队 7003  

其他男歌手 4001  

其他女歌手 4002  

其他组合/乐队 4003  
```
**接口地址：** `/artist/list`   
**调用示例：** `/artist/list?cat=1001`  

#### 收藏/取消收藏歌手    
说明：调用此接口，可获取收藏的歌手列表  

**必选参数：** `artistId :` 歌手id `t:` 操作，1为收藏，其他为取消收藏  
**接口地址：**  `/artistId/sub`  
**调用示例：** `/artistId/sub?id=6452&t=1`  

#### 收藏的歌手列表  
说明： 调用此接口（需登录）、可获取收藏的歌手列表   

**接口地址：**  `/artist/sublist`  
**调用示例：**  `/artist/sublist`  

#### 收藏视频  
说明：调用此接口（需登录），可收藏视频  

**必选参数：**  `id: ` 视频id   `t: ` 1为收藏，其他为取消收藏  
**调用接口：**  `/video/sub`  
**调用示例：**  `/video/sub?id=121212`  

#### 收藏mv  
说明：调用此接口(需登录)，可收藏 mv  

**必选参数：**  `id:` mv的id   `t: ` 1为收藏mv，其他为取消收藏mv  
**调用接口：**  `/mv/sub`  
**调用示例：**  `/mv/sub`  

#### 歌单分类  
说明： 调用此接口，获取歌单分类  

**接口地址：**  `/playlist/catlist`  
**调用示例：**  `/playlist/catlist`  

####  热门歌单分类  
说明：调用此接口，获取热门歌单分类  

**调用接口：**  `playlist/hot`  
**调用示例：**  `/playlist/hot`  

#### 歌单（网友精选碟）  
说明： 调用此接口， 获取网友精选歌单碟  

**可选参数：**  
```
    order: 可选值为new、hot （最新、最热）  

    cat: tag 比如 " 华语 "、" 古风 " 、" 欧美 "、" 流行 ", 默认为 "全部",可从歌单分类接口获取(/playlist/catlist)   

``` 
**接口地址：**  `/top/playlist`  
**调用示例：**  `/top/playlist?limit=10&order=new`    

#### 获取精品歌单  
说明： 调用此接口，可获取精品歌单  

**可选参数：**
```
    cat: tag 比如 " 华语 "、" 古风 " 、" 欧美 "、" 流行 ", 默认为 "全部",可从歌单分类接口获取(/playlist/catlist)  

    limit: 歌单数，默认为20  

    before： 分页参数，取上一页最后一页歌单  
    
    updateTime  获取下一页数据  

```
**接口地址：**  `/top/playlist/highuality`  
**调用示例：**  `/top/playlist/highuality?before=1503639064232&limit=3`  

#### 相关歌单推荐  
说明：调用此接口，可获取相关歌单推荐  

**必须参数：**  `id:` 歌名id  
**可选参数：**  `s:`  歌单s收藏者  
**接口地址：**  `/playlist/detail`  
**调用示例：**  `/playlist/detail?id=24381616`  

#### 获取音乐的url  
说明： 使用歌单详情接口后 , 能得到的音乐的 id, 但不能得到的音乐 url, 调用此接口 , 传入的音乐 id( 可多个 , 用逗号隔开 ), 可以获取对应的音乐的 url( 不需要登录 )  

!> 注 : 部分用户反馈获取的 url 会 403,hwaphon找到的 解决方案是当获取到音乐的 id 后，将 https://music.163.com/song/media/outer/url?id=id.mp3 以 src 赋予 Audio 即可播放  

**必选参数：**  `id:` 音乐的id
**可选参数：**  `br:` 码率,默认设置了 999000 即最大码率,如果要 320k 则可设置为 320000,其他类推  
**调用地址：**  `/song/url`  
**调用示例：**  `/song/url?id=33894312`  

#### 音乐是否可用  
说明：调用此接口,传入歌曲 id, 可获取音乐是否可用,返回 `{ success: true, message: 'ok' }` 或者 `{ success: false, message: '亲爱的,暂无版权' }`  

**必选参数：**  `id: `  歌曲id  
**可选参数：**  `br: `  码率,默认设置了 999000 即最大码率,如果要 320k 则可设置为 320000,其他类推  
**接口地址：**  `/check/music`  
**调用示例：**  `/check/music?id=33894312`    

#### 搜索  
说明：调用此接口，传入搜索关键词可以搜索该音乐/专辑 / 歌手 / 歌单 / 用户 , 关键词可以多个 , 以空格隔开 , 如 " 周杰伦 搁浅 "( 不需要登录 ), 搜索获取的 mp3url 不能直接用 , 可通过 /song/url 接口传入歌曲 id 获取具体的播放链接  

**必选参数：** `keywords: `  关键词  
**接口地址：** `/search`  
**调用示例：** `/search?keywords=沙漠骆驼`  

#### 热搜  
说明：调用此接口，可以获取热搜  

**接口地址：** `/search/hot`  
**调用示例：** `/search/hot?keywords=''`  

#### 搜索建议  
说明：调用此接口，传入搜索关键词可以获得搜索建议哟  

**必选参数：** `keywords` 搜索关键词  
**接口地址：** `/search/suggest`  
**调用示例：** `/search/suggest?keywords=say hello`  

#### 搜索多重匹配  
说明：调用此接口，传入关键词可获取搜索结果 

**必选参数：** `keywords`  
**接口地址：** `/search/multimatch`  
**调用示例：** `/search/multimatch?keywords=沙漠骆驼`  

#### 新建歌单  
说明：调用该接口，传入歌单名可新建歌单  

**必选参数：** `name` 
**接口地址：** `/playlist/create`  
**调用示例：** `/playlist/create?name=沙漠骆驼`  

#### 收藏/取消收藏歌单  
说明：调用此接口，传入类型和歌单id可收藏歌曲  

**必选参数：** `t`：类型 1.收藏，2.取消收藏  `id` 歌曲id
**接口地址：** `/playlist/subscribe`  
**调用示例：** `/playlist/subscribe?t=1&id=106697785`  

#### 对歌单进行添加或删除歌曲  
说明： 嗲用此接口，可以添加歌曲到歌单或者从歌单中删除（取消）  

**必选参数：** 
```
 op: 修改歌单 add 添加 del 删除  
 
 pid: 歌单id  

 tracks: 多个歌曲id可用逗号隔开  
```
**接口地址：** `/playlist/tarcks` 
**调用示例：** `/playlist/tarcks?op=add&pid=24381616&tracks=347231`( 对应把歌曲添加到 ' 我 ' 的歌单 , 测试的时候请把这里的 pid 换成你自己的, id 和 tracks 不对可能会报 502 错误)  

#### 获取歌词  
说明： 调用此接口，传入音乐id可获取该音乐歌词  

**必选参数：** `id` 歌曲id  
**调用接口：** `/lyric`  
**调用示例：** `/lryic?id=33894312`  

#### 新歌速递  
说明：调用此接口，可获取新歌速递  

**必须啊参数：**
```
type: 地区类型id：
    全部： 0  
    华语： 7  
    欧美： 96  
    日本： 8  
    韩国： 16  
```
**接口地址：** `/top/song`       
**调用示例：** `/top/song?type=0`  

#### 歌曲评论  
说明： 调用此接口，传入歌曲id和limit，可获取该音乐的所有评论（不需要登录）  

**必选参数：**  `id`： 音乐id  
**可选参数：**  `limit`：取出评论数，默认为20  
**调用接口：**  `/comment/music`  
**调用示例：**  `/comment/music?id=186016&limit=30`  

#### 专辑评论  
说明：调用此接口，传入音乐id和limit参数，获取该专辑的所有评论（不需要登录）  

**必选参数：**  `id` 该首专辑id  
**可选参数：**  `limit` 取出评论数， 默认20 `offset` 偏移量 用于分页 如 :( 评论页数 -1)*20, 其中 20 为 limit 的值  
**调用接口：**  `/comment/album`  
**调用示例：**  `/comment/album?id=32311&limit=30`  

#### mv评论  
说明：调用此接口，传入音乐id和limit参数，即可获得mv评论详情  

**必选参数：** `id`: mv id
**可选参数：** `limit`: 取出评论数 默认为20 `offset`: 偏移量，用于分页
**接口地址：** `/comment/mv`  
**调用示例：** `/comment/mv?id=5436712`  

#### 电台节目评论  
说明：调用此接口，传入`id` 和 `limit` 可获取得电台节目评论详情  

**必选参数：** `id`: 单台节目id  
**可选参数：** `limit` 取出评论数， 默认20 `offset` 偏移量 用于分页 如 :( 评论页数 -1)*20, 其中 20 为 limit 的值 
**接口地址：**  `/comment/dj`  
**调用示例：**  `/comment/dj?id=794062371&limit=30`  

#### 视频评论 
说明： 、传入 `id` 和 `limit` 获取视频评论详情  

**必选参数：**  `id`: 视频 id  
**可选参数：**  `limit`: 评论数、默认20  
**接口地址：**  `/comment/video`  
**调用示例：**  `/comment/video?id=89ADDE33C0AAE8EC14B99F6750DB954D&limit=30`  

#### 热门评论  
说明:调用此接口,传入`type`和`id`参数,可获得所有评论(不需要登录)  

**必选参数:** `id:` 资源id 
`type`: 数字，资源类型，对应歌曲，mv 专辑 电台 视频  
```
 0: 歌曲  
 1: mv  
 2: 歌单  
 3: 专辑  
 4: 电台  
 5: 视频  
```
**接口地址:** `/comment/hot`  
**调用例子:** `/comment/hot?id=186016&type=0`  

#### banner  
说明：调用此接口可获取轮播图数据  

**接口地址：**  `/banner`  
**调用示例：**  `/banner`  


#### 资源点赞（MV，电台，视频）  
说明： 调用此接口，获取 mv 电台 视频 点赞 

**必选参数：**
`type:` 有一下几种类型  
```
1: MV  
2: 电台  
3: 视频  
```
`t:` 操作，1为点赞 其他为取消  
`id:` 资源 id  
**接口地址：** `/resource/like`  
**调用示例：** `/resource/like?t=1&type=1&id=5436712`  

#### 获取歌曲详情  




