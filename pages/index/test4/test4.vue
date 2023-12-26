<template>
	<view>
		<button type="primary" @click="button1">查看本地图片信息</button>
		<button type="primary" @click="button2">查看网络图片信息</button>
	</view>
</template>

<script>
	export default {
		data() {
			return {

			}
		},
		methods: {
			button1() {
				uni.getImageInfo({
					src:'/static/logo.png',
					success: (data) => {
						console.log(data);
					},
					fail: (err) => {
						console.log("错误",err);
					}
				})
			},
			button2() {
				uni.getImageInfo({
					src:'https://qiniu-web-assets.dcloud.net.cn/unidoc/zh/uni-app.png',
					success: (data) => {
						console.log(data);
					},
					fail: (err) => {
						console.log("错误",err);
					}
				})
			}
		}
	}
</script>

<style>
button{
	margin: 5px;
}
</style>