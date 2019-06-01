<template>
	<view class="content">
		<navigation-custom :config="config" :scrollTop="scrollTop" @customConduct="customConduct" :scrollMaxHeight="scrollMaxHeight"/>
		<!-- <navigation-custom  /> -->
	</view>
</template>

<script>
	import navigationCustom from "../../components/struggler-navigationCustom/navigation-custom"
	export default {
		data() {
			return {
				config:{
					title:"我是标题", //title
					bgcolor:"#c1a379", //背景颜色
					// fontcolor:"red", //文字颜色，默认白色
					type:3, //type 1，3胶囊 2，4无胶囊模式
					transparent:true, //是否背景透明 默认白色
					linear:true, //是为开启下滑渐变
					share:true, //是否将主页按钮显示为分享按钮
					menuIcon:"../../static/icon/back_.png", //当type为3或者4的时候左边的icon文件位置，注意位置与当前页面不一样
					//menuText:"返回", //当type为3或4的时候icon右边的文字
				},
				scrollTop:0 ,// 当linear为true的时候需要通过onpagescroll传递参数
				scrollMaxHeight:200 //滑动的高度限制，超过这个高度即背景全部显示
			}
		},
		onPageScroll(e) {
			this.scrollTop = e.scrollTop;
		},
		onLoad() {

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
</script>

<style>
	page{
		width: 100%;
		height: 100%;
		background-color: #8F8F94;
	}
	.content {
		text-align: center;
		height: 2400upx;
	}

	.logo {
		height: 200upx;
		width: 200upx;
		margin-top: 200upx;
	}

	.title {
		font-size: 36upx;
		color: #8f8f94;
	}
</style>
