

# uniapp 小程序自定义导航栏

微信小程序自定义导航栏组件，ios与android端都可以和右边的胶囊对齐，使用环境为 `uni-app`。  
  

## 如何获取
github仓库: [https://github.com/strugglerx/uniapp_navigation_custom](https://github.com/strugglerx/uniapp_navigation_custom)  
  
## props
| 参数|描述|类型|默认值|
|--|--|--|--|
|config|配置|object|	{title:"",bgcolor:"",type:2,linear:false,transparent:false,fontcolor:"#000",menuIcon:"",menuText:""}|
|scrollTop|滑动高度|number|0|
|scrollMaxHeight|滑动最高高度|number|288|

## 如何使用
*.vue
```html
<navigation-custom :config="config" :scrollTop="scrollTop" @customConduct="customConduct" :scrollMaxHeight="scrollMaxHeight"/>
```
  
```javascript
	import navigationCustom from "../../components/navigation-custom"
	export default {
		data() {
			return {
				config:{
					title:"我是标题", //title
					bgcolor:"#c1a379", //背景颜色
					// fontcolor:"red", //文字颜色，默认白色
					type:2, //type 1，3胶囊 2，4无胶囊模式
					transparent:true, //是否背景透明 默认白色
					linear:true, //是为开启下滑渐变
					share:true, //是否将主页按钮显示为分享按钮
					// menuIcon:"../static/icon/back_.png", 当type为3或者4的时候左边的icon文件位置，注意位置与当前页面不一样
					// menuText:"返回", 当type为3或4的时候icon右边的文字
				},
				scrollTop:0 ,// 当linear为true的时候需要通过onpagescroll传递参数
				scrollMaxHeight:200 //滑动的高度限制，超过这个高度即背景全部显示
			}
		},
		onPageScroll(e) {
			this.scrollTop = e.scrollTop;
		},
		components:{
			navigationCustom
		},
		methods: {
			//当config type 为 4或者3 的时候 自定义methods
			customConduct(){
				console.log("ssssss")
			}
		}
	}
```
  
## 实际效果

![android](https://github.com/strugglerx/uniapp_navigation_custom/blob/master/11559401153_.pic_hd.jpg?raw=true)
![ios](https://github.com/strugglerx/uniapp_navigation_custom/blob/master/21559401194_.pic_hd.jpg?raw=true)
![type=3](https://github.com/strugglerx/uniapp_navigation_custom/blob/master/31559402181_.pic_hd.jpg?raw=true)
![](https://github.com/strugglerx/uniapp_navigation_custom/blob/master/41559402198_.pic_hd.jpg?raw=true)



## 反馈问题
如在使用中发现bug或有优化的建议和意见，请发邮件 <str@li.cm> 或在 [gitHub](https://github.com/strugglerx/uniapp_navigation_custom) 上反馈。
  
## 更新日志

2019.6.3 *v0.0.2*  返回主页修改为switchTab 

2019.6.1 *v0.0.1*  创建本插件  
  