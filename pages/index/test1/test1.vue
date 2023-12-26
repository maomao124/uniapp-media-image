<template>
	<view>
		<button  type="primary" @click="button1">选择图片</button>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			}
		},
		methods: {
			button1()
			{
				uni.chooseImage({
					count: 8,
					sizeType: ['original', 'compressed'],
					sourceType: ['album'], //从相册选择
					success: function (res) {
						console.log(JSON.stringify(res.tempFilePaths));
					}
				});
			}
		}
	}
</script>

<style>

</style>
