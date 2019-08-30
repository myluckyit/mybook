# 瑶池接口文档

## 基础路径：http://ycy.jszero.cn/

## 首页

1、轮播图

接口：carousel/list

请求方式：get

参数：position_id，
	   值：1：表示头部轮播图；2：底部轮播图；

2、滚动广告

接口：adver/list

请求方式：get

3、VR

接口：vr/list

请求方式：get

返回数据：

```
{
	"id": 1,
	"x": "234",
	"y": "310.125",
	"href": "https://720yun.com/t/dd5jedeasv0?scene_id=15524836",
	"type": 1,
	"img_url1": "",
	"img_url2": "",
	"img_url3": "",
	"img_url4": "",
	"img_url5": ""
}

数据说明：
 type：值为1表示VR效果图，2表示普通图片。

```

4、首页攻略图

接口：index_tips/list

请求方式：get

## 文章

1、文章列表

接口：news/list

请求方式：get

参数：page，值：0，表示请求第一页文章列表，不传默认获取第一页数据。
			1,表示请求第二页文章数据，以此类推

返回数据：

show_type_id，值为1时表示只有一张图片
			    值为2时表示有三张图片
```
{
	brief: "新华社摩纳哥3月24日电（记者陈贽　许林贵）国家主席习近平24日同摩纳哥亲王阿尔贝二世举行会谈。"
	cover_img_url1: "http://yaochiwan.bluej.cn/files/upload-1553499343015.jpg"
	cover_img_url2: ""
	cover_img_url3: ""
	format_content: "<p fr-original-style="line-height: 30px; text-align: left; color: rgb(51, 51, 51);" style="line-height: 30px; text-align: left; color: rgb(51, 51, 51); box-sizing: inherit;">&nbsp; &nbsp; &nbsp; &nbsp; 习近平指出，很高兴应亲王殿下邀请对摩纳哥公国进行国事访问。这是中国国家主席首次访问摩纳哥。我们两国相似的民族性格和共同的精神追求，使得我们相知相亲。中摩建交20多年来，双方始终真诚友好、平等相待。当前，中摩双边关系稳步发展，务实合作与时俱进，尤其是在环保、电信、移动支付等新领域走在中欧合作前列。中摩关系已成为不同大小、不同历史文化、不同社会制度国家友好交往的典范。 <span style="box-sizing: inherit;" fr-original-style="[object Object]: undefined;"></span></p><p data-f-id="pbf" style="text-align: center; font-size: 14px; margin-top: 30px; opacity: 0.65; font-family: sans-serif;">Powered by <a href="https://www.froala.com/wysiwyg-editor?pb=1" title="Froala Editor">Froala Editor</a></p>"
	id: 2
	orders: 2
	origin_content: ""
	show_type_id: 1
	stars: 5
	title: "习近平同摩纳哥亲王阿尔贝二世举行会谈"
	views: 537
}
```

2、文章详情数据和浏览量

接口：news/addViews

请求方式：get

请求参数：id（新闻id）

反回值：此id对应的新闻内容。

3、轮播图

接口：news_carousel/list

请求方式：get

返回数据

```
{
	id: 1
	img_url: "http://yaochiwan.bluej.cn/files/upload-1553499801591.jpg"
	news_id: 0
	orders: 1
}
```

## 攻略

1、景点列表

接口：tips/list

请求方式：get

参数：page，值：0，表示请求第一页列表，不传默认获取第一页数据。
			1,表示请求第二页数据，以此类推


## 动态

1、动态页列表

接口：dynamic/list

请求方式: GET

参数：page，值：0，表示请求第一页列表，不传默认获取第一页数据。
			1,表示请求第二页数据，以此类推


返回数据：

```
[
	{
		id: 3
		img_url1: "http://yaochiwan.bluej.cn/files/upload-1553501131327.jpg"
		img_url2: "http://yaochiwan.bluej.cn/files/upload-1553501142010.png"
		img_url3: "http://yaochiwan.bluej.cn/files/upload-1553501151856.png"
		orders: 3
		type_id: 3
	}
]

数据说明：
type_id:表示渲染的模板
值：1、表示三列式渲染模板
    2、左边一张大图，右边二张小图
    3、左边2张小图，右边一个大图

```

## 招聘

1、招聘列表

接口：jobs/list

请求方式：get

参数：page，值：0，表示请求第一页列表，不传默认获取第一页数据。
			1,表示请求第二页数据，以此类推


## 预约

1、景点景区

接口：reser/scenic/list

请求方式：get

参数：page，值：0，表示请求第一页列表，不传默认获取第一页数据。
			1,表示请求第二页数据，以此类推


2、酒店住宿

接口：reser/hotel/list

请求方式：get

参数：page，值：0，表示请求第一页列表，不传默认获取第一页数据。
			1,表示请求第二页数据，以此类推


3、美食餐饮

接口：reser/food/list

请求方式：get

参数：page，值：0，表示请求第一页列表，不传默认获取第一页数据。
			1,表示请求第二页数据，以此类推


