# API 列表

[GET] /select_labels

[POST] [PUT] [DELETE] /select_labels/:labelname

[POST] [PUT] [DELETE] [GET] /selects

----------

## 指令：[GET] /select_labels

说明
	
	【任意】返回精选栏目
		
Example Request：
	
	GET /select_labels HTTP/1.1 
	Accept: application/json
	

返回数据说明：
	
	labels  数据精选栏目名称数组

返回值示例

	{
	    "labels": [
	        {
	            "labelname": "股市行情",
	            "order": 1
	        }{
	            "labelname": "终端信息",
	            "order": 1
	        }{
	            "labelname": "天气预报",
	            "order": 1
	        }{
	            "labelname": "医疗",
	            "order": 1
	        }
	    ]
	}

## 指令：[POST] /select_labels/:labelname

说明
	
	【管理员】创建精选栏目

输入参数说明：
	
	labelname 精选栏目条目名称
	order	  精选栏目排序（1-100， 排序越大越靠前）
		
Example Request：
	
	POST /select_labels/股市行情 HTTP/1.1 
	Accept: application/json
	Authorization: Basic akmklmasadalkm==

Example Response：
	
	无

## 指令：[PUT] /select_labels/:labelname

说明
	
	【管理员】更新现有精选栏目的名称
	 	
	 newlabelname 	要改成的名字
	 order	  		精选栏目排序（1-100， 排序越大越靠前）
	
输入参数说明：
	
	newlabelname 新精选栏目条目名称
	[URL]中labelname 为需要修改的名字
		
Example Request：
	
	POST /select_labels/股市行情 HTTP/1.1 
	Accept: application/json
	Authorization: Basic akmklmasadalkm==
	
	{
		newlabelname：2015股市行情
		order：100
	}

Example Response：
	
	无

## 指令：[DELETE] /select_labels/:labelname

说明

	【管理员】删除精选栏目
	
输入参数说明：
	
	无
		
Example Request：
	
	DELETE /select_labels/股市行情 HTTP/1.1 
	Accept: application/json
	Authorization: Basic akmklmasadalkm==

Example Response：
	
	无

## 指令：[GET] /selects

说明
	
	【任意】返回精选内容
		
Example Request：
	
	GET /selects HTTP/1.1 
	Accept: application/json

Example Response：

	{
	    "selects": [
	        {
	            "repname": "",
	            "itemname": ""
	        },
	        {
	            "repname": "",
	            "itemname": ""
	        },
	        {
	            "repname": "",
	            "itemname": ""
	        }
	    ]
	}


返回数据说明：
	
	selects： repname和itemname的数组

返回值示例
	
	    {
	        "selects": [
	            {	
	                "repname": "上海",
	                "itemname": "上海终端"
	            },
	            {
	                "repname": "北京",
	                "itemname": "北京终端"
	            },
	            {
	                "repname": "深圳",
	                "itemname": "深圳终端"
	            }
	        ],
	    }
	
## 指令：[POST] /selects

说明
	
	【管理员】创建精选内容

输入参数说明：
	
	 repname[必选]: 		　
	 itemname[必选]: 
	 select_labels[必选]：　			    	精选栏目项
	 order[可选，默认为1，值越大排名越靠前]   	精选排序功能 
		
Example Request：
	
	POST /selects HTTP/1.1 
	Accept: application/json
	Authorization: Basic akmklmasadalkm==

返回值示例
	
	无

## 指令：[PUT] /selects

说明

	【管理员】更新精选内容

输入参数说明：
	
	 repname[必选]: 		　
	 itemname[必选]: 
	 select_labels[必选]：　								精选栏目项
	 order[可选，默认为1，值越大排名越靠前]   	精选排序功能 
		
Example Request：
	
	PUT /selects HTTP/1.1 
	Accept: application/json
	Authorization: Basic akmklmasadalkm==

返回值示例

	无
	
## 指令：[DELETE] /selects

说明

	【管理员】删除精选内容

输入参数说明：
	
	 repname[必选]: 		　
	 itemname[必选]: 
	 select_labels[必选]：　精选栏目项
		
Example Request：
	
	DELETE /selects HTTP/1.1 
	Accept: application/json
	Authorization: Basic akmklmasadalkm==

Example Response：

	无