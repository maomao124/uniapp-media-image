<template>
	<view>
		<button type="primary" @click="button1">选择图片保存</button>
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
				uni.chooseImage({
					count: 1,
					sizeType: ['original', 'compressed'],
					sourceType: ['album'], //从相册选择
					success: function(res) {

						uni.saveImageToPhotosAlbum({
							filePath: res.tempFilePaths[0],
							success: (data) => {
								console.log(data);
							},
							fail: (err) => {
								console.log("错误：", err);
							}
						})
					}
				});
			}
		}
	}
</script>

<style>

</style>