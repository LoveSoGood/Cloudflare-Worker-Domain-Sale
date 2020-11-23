# Cloudflare-Worker-Domain-Sale

Cloudflare-Worker-Domain-Sale是一款基于Cloudflare-Worker平台上的云函数程序，可以使用它瞬间搭建属于自己的域名停放页面，提供丰富的自定义配置，帮助您尽快售出自己域名。

🎉[演示地址](https://96596.net)

## 程序安装
### 快速安装
1. 在 [Cloudflare Worker](https://workers.cloudflare.com/) 管理页面创建一个新的 **Worker** 。
2. 在Worker编辑页面左边粘贴 `index.js` 中的代码。
3. 根据自身需要修改 `config` 的配置内容
### 进阶安装
> 如何绑定自己的域名
1. 根据上文快速安装完成，回到域名管理面板
2. 点击 `Workers` 进入Workers管理页面
3. 点击 `Add route` 设置新的路由
4. `Route` 可以输入自己想使用的子域名，如果在根域名上使用直接把当前域名输入即可，`Worker` 选择上文快速安装好的Worker
> `Route` 所使用的域名地址**必须已经解析好A记录**，如果没有能绑定的IP地址，可以输入8.8.8.8占位：）

## 系统配置

CF-Worker-Dir允许用户自定义导航页面，配置内容如下：
```
const config = {
  title: "自定义导航",                 //自定义网站标题
  subtitle: "Cloudflare Workers Nav", //自定义网站副标题
  logo_icon: "sitemap",               //选择网站logo icon 暂时只支持 (eg:https://semantic-ui.com/elements/icon.html)
  hitokoto: true,                     //开启 格言 插件
  search:true,                        //开启 搜索 功能  
  search_engine:[                     //搜索引擎列表
    {
      name:"百度一下",                   //搜索引擎名称
      template:"https://www.baidu.com/s?wd=$s"  //搜索引擎模板（含关键词$s）
    }
  ],
  selling_ads: true,                  //是否要开启网址推广
  sell_info:{
    domain:"example.com",             //当前域名
    price:500,                        //价格
    mon_unit:"yen sign",              //货币单位 (eg:https://semantic-ui.com/elements/icon.html#computers)
    contact:[                         //联系方式
      {
        type:"envelope",              //通讯工具 ("weixin","qq","telegram plane","envelope" or "phone")
        content:"info@example.com"    //号码/地址
      }
    ]                        
  },

```
## Licence

MIT

## 由衷感谢

特别感谢@sleepwood

代码修改自 https://github.com/sleepwood/CF-Worker-Dir
