<template>
	<view>
		<button type="primary" @click="button1">预览图片</button>
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
					count: 8,
					sizeType: ['original', 'compressed'],
					sourceType: ['album'], //从相册选择
					success: function(res) {
						uni.previewImage({
							urls: res.tempFilePaths,
							longPressActions: {
								itemList: ['发送给朋友', '保存图片', '收藏'],
								success: function(data) {
									console.log('选中了第' + (data.tapIndex + 1) + '个按钮,第' + (data
										.index + 1) + '张图片');
								},
								fail: function(err) {
									console.log(err.errMsg);
								}
							}
						});
						setTimeout(function(){
							uni.closePreviewImage({
								success: () => {
									console.log("关闭成功");
								}
							})
						},1000)
					}
				});
			}
		}
	}
</script>

<style>

</style>