# APISpace 介绍
**本 API 服务由 [APISpace（apispace.com）](https://www.apispace.com/?utm_source=github&utm_term=ipguishudi) 提供。**

APISpace 是 Eolink 旗下专业的 API 开放与交易平台，为广大企业以及个人开发者提供多维度、全方位的API接口，覆盖短信验证、天气查询、快递物流、OCR文字识别等海量 API 服务，帮助用户快速获取数据，降低获取数据的成本和难度，提升开发效率。

APISpace 提供15种开发语言的代码示例，分别是：
- Java(OK HTTP)
- HTTP
- cURL
- 微信小程序
- PHP(pecl_http)、PHP(cURL)
- Python(http.client)、Python(Requests)
- JavaScript(Jquery AJAX)、JavaScript(XHR)
- NodeJS(Native)、NodeJS(Request)
- Ruby(Net:Http)
- Shell(Httpie)、Shell(cUrl)

# IP归属地-IPv4区县级

根据IP地址查询归属地信息，包含43亿全量IPv4，支持到中国地区（不含港台地区）区县级别，含运营商数据。

**使用该产品前，您需要通过 [https://www.apispace.com/eolink/api/ipguishu/introduction](https://www.apispace.com/eolink/api/ipguishu/introduction?utm_source=github&utm_term=ipguishudi) 申请API服务**

本文档末尾提供了 Python(Requests) 的调用代码示例，可以前往文档末尾查看。

更多代码示例：[https://www.apispace.com/eolink/api/ipguishu/guidence/](https://www.apispace.com/eolink/api/ipguishu/guidence/?utm_source=github&utm_term=ipguishudi)

### API 版本说明

IPv4归属地查询分为 **高精版**、**区县级**、**城市级**，共3个版本。

本接口为 IPv4 归属地 区县级，查看更多：

-   [IPv4 归属地 高精版](https://www.apispace.com/eolink/api/ipv4street/introduction?utm_source=github&utm_term=ipguishudigaojing)

-   [IPv4 归属地 城市级](https://www.apispace.com/eolink/api/ipv4city/introduction?utm_source=github&utm_term=ipguishudicity)  
      


|      | IPv4归属地-高精版                                                          | IPv4归属地-区县级                                                             | IPv4归属地-城市级                                    |
| ---- | -------------------------------------------------------------------- | ----------------------------------------------------------------------- | ---------------------------------------------- |
| 适用人群 | 对定位精度要求比较高的企业用户                                                      | 企业或个人开发者                                                                | 企业或个人开发者                                       |
| 数据描述 | ● 43亿全量IPv4 ● **中国地区（不含港台地区）街道级别，定位至50米** ● IP最新出现位置，覆盖更全范围 ● 含运营商数据 | ● 43亿全量IPv4 ● **中国地区（不含港台地区）区县级别，定位至区县中心** ● IP地址历史位置聚类，去除无效范围 ● 含运营商数据 | ● 43亿全量IPv4 ● **中国大陆地区（不含港澳台地区）城市级别** ● 含运营商数据 |
| 更新频率 | 每周更新                                                                 | 每日更新                                                                    | 每日更新                                           |
| 坐标系  | GPS和百度                                                               | GPS和百度                                                                  | GPS和百度                                         |
| 区域类型 | 单区域或多区域                                                              | 单区域                                                                     | 单区域                                            |
| 在线并发 |  1000次/秒                                                             |  1000次/秒                                                                |  1000次/秒                                       |


### 应用场景
#### 1. 匿名访客识别，挖掘更多销售线索
用作网站的匿名访客识别，通过解析网站访问用户留存的IP地址，识别访问用户的所属企业、经营地址、官网、联系方式等信息，进而分析来访用户与自身经营业务的匹配程度，挖掘更多的销售线索，辅助业务增长。

#### 2. 建立用户轨迹画像，分析用户需求，辅助产品营销
通过解析已存用户不同登录网站或者APP时间的IP地址，了解用户的地理位置信息，进行用户轨迹画像绘制，通过分析用户常涉区域的经营消费水平，推测用户的理财能力与偏好，根据推导结果进行理财产品匹配，辅助制定营销策略。

#### 3. 互联网在线广告精准投放
对用户进行IP地址解析，了解用户所处的地理位置，同时根据用户所处地理位置的消费水平，对指定半径范围内用户推送适宜的产品。

#### 4. 位置交叉核验，评估用户可信任度
首先根据商户登录的IP地址进行地理位置解析了解用户的真实所处位置，随后利用解析结果与经营注册地址进行匹配校对，判断商户登录位置与经营位置是否一致，作为评估商户可信任程度的风险入参之一。

#### 5. 互联网金融行业风险控制
通过解析用户登录的IP地址了解用户的地理位置位置信息，首先与内部已掌握的风险区域进行数据对比，判断是否发生在高风险地区，同时对同一时间段不同交易用户的IP地址进行解析，了解交易发生地的分布情况，判定是否存在多笔交易发生地聚集，进而辅助内部风控体系建设。

### 返回示例

```
{
    “code”: “Success”,
    “data”: {
        “continent”: “亚洲”,
        “country”: “中国”,
        “owner”: “imported inetnum object for IIINT”,
        “isp”: “China Education and Research Network Center,Tsinghua University,Beijing 100084”,
        “zipcode”: “100038”,
        “timezone”: “UTC+8”,
        “accuracy”: “城市”,
        “source”: “数据挖掘”,
        “areacode”: “CN”,
        “adcode”: “110100”,
        “asnumber”: “4538”,
        “lat”: “40.009424”,
        “lng”: “116.332556”,
        “radius”: “105.2321”,
        “prov”: “北京市”,
        “city”: “北京市”
    },
    “charge”: true,
    “msg”: “查询成功”,
    “ip”: “166.111.4.100”,
    “coordsys”: “WGS84”
}
```

### 技术原理

IP归属地是利用大数据挖掘和大规模网络探测技术，对IP地址的基础信息和网络拓扑数据进行采集、处理， 结合IP地址所在的应用场景与网络属性等因素，利用动态密度聚类算法和基于多层神经网络的IP地址定位算法，完成IP地址地理位置定位。

![image](https://user-images.githubusercontent.com/36323798/223399783-82ad92be-7dfe-4ea6-837d-f73155a4caa7.png)


### Python(Requests) 调用代码示例

```
import requests

url = "https://eolink.o.apispace.com/ipguishu/ip/geo/v1/district"

payload = {"ip" : "1.45.124.145","coordsys" : "WGS84"}

headers = {
    "X-APISpace-Token":"",
    "Authorization-Type":"apikey"
}

response=requests.request("GET", url, params=payload, headers=headers)

print(response.text)
```
