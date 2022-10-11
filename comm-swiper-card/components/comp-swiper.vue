<template>
	<view class="swiperWrapper">
		<view class="swiperCenter">
			<view class="swiperItem first" @touchstart="moveItem1Start" @touchmove="moveItem1" @touchend="moveItem1End" :style="firstItemStyle">
				<image class="img" :src="cardList[0].src" mode="scaleToFill"></image>
			</view>
			<view class="swiperItem mid">
				<image class="img" :src="cardList[1].src" mode="scaleToFill"></image>
			</view>
			<view class="swiperItem end">
				<image class="img" :src="cardList[2].src" mode="scaleToFill"></image>
			</view>
		</view>
			<!-- <text class="title">{{cardList[0].title}}</text> -->
	</view>
</template>
<script>
export default{
	props: {
		cardDatas: {
			type: Array
		}
	},
	data() {
		return {
			StartX: 0,
			firstItemStyle: '',
			opacity: '1',
			cardList: []
		}
	},
	onReady() {
		this.cardList = this.$props.cardDatas
		console.log(this.cardList, this.$props.cardDatas, '哈哈哈')
	},
	methods: {
		moveItem1Start(e) {
			this.StartX = e.changedTouches[0].clientX
		},
		moveItem1(e){
			let x = e.changedTouches[0].clientX
			let newOpacity = (x/this.StartX)*1
			let lateX = this.StartX - x
			this.firstItemStyle = `transform: translateX(-${lateX}rpx); opacity: ${newOpacity}`
		},
		moveItem1End(e){
			let x = e.changedTouches[0].clientX
			console.log(this.StartX - x)
			if((this.StartX - x) > 100) {
				setTimeout(() => {
					let temp = this.cardList[0]
					this.cardList.shift()
					this.cardList.push(temp)
				}, 10)
			}
			this.firstItemStyle = 'left: 50rpx'
			this.opacity = 1
		}
	}
}
</script>

<style lang="scss" scoped>
	.swiperWrapper{
		width: 750rpx;
		height: 900rpx;
		background: linear-gradient(to bottom, #ffffff, #f2ebd9);
		
		.swiperCenter{
			width: 100%;
			height: 100%;
			position: relative;
			
			
			.swiperItem{
				width: 600rpx;
				height: 800rpx;
				border-radius: 10rpx;
				position: absolute;
				top: 20rpx;
				left: 50rpx;
				
				.img{
					width: 100%;
					height: 100%;
				}
			}
			
			.first{
				z-index: 99;
			}
			.mid{
				z-index: 50;
				top: 35rpx;
				left: 70rpx;
			}
			.end{
				z-index: 9;
				top: 50rpx;
				left: 90rpx;

			}
			
		}
		// .title {
		// 	font-size: 20rpx;
		// 	position: absolute;
		// 	top: 860rpx;
		// 	left: 50rpx;
		// 	z-index: 998;
		// }
		
		
	}
</style>