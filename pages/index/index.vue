<template>
	<view class="content">
		<!-- <mix-loading v-if="isLoading" :type="2"></mix-loading> -->
	

		<!-- <mix-modal ref="mixModal" title="提示" text="您确定要退出登录吗" @onConfirm="logout"></mix-modal> -->
		<mix-upload-image :length='5' ref="mixUploadImage" @onChange="onChange"></mix-upload-image>
		
			<button @click="logout">退出登录</button>
	</view>
</template>

<script>
	import mixUploadImage from "@/components/mix-upload-image/mix-upload-image.vue"
	export default {
		components: {
			mixUploadImage
		},
		data() {
			return {
				title: 'Hello'
			}
		},
		onLoad() {

		},
		methods: {
			onChange(e){
				console.log(e)
			},
			logout() {
			  const  img=this.$refs.mixUploadImage.imageList.map(item=> item.url);
			  console.log(img)
			},
		}
	}
</script>

<style>
	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}

	.logo {
		height: 200rpx;
		width: 200rpx;
		margin-top: 200rpx;
		margin-left: auto;
		margin-right: auto;
		margin-bottom: 50rpx;
	}

	.text-area {
		display: flex;
		justify-content: center;
	}

	.title {
		font-size: 36rpx;
		color: #8f8f94;
	}
</style>
