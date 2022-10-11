<template>
	<commp-swiper :cardDatas="cardList" />
</template>

<script>
	import commpSwiper from "@/components/comp-swiper.vue"
	export default {
		components: {
			commpSwiper
		},
		data() {
			return {
				cardList: [
					{
						id: 1,
						color: "blue",
						src: 'https://img2.baidu.com/it/u=30735538,1747473852&fm=253&fmt=auto&app=138&f=JPEG?w=333&h=500',
						title: '即将举行 | 10月10日-25日 北京时间'
					},
					{
						id: 2,
						color: 'seagreen',
						src: 'https://img0.baidu.com/it/u=1428736186,2906314628&fm=253&fmt=auto&app=138&f=JPEG?w=500&h=625',
						title: '即将举行 | 10月10日-25日 南京时间'
					},
					{
						id: 3,
						color: 'bisque',
						src: 'https://img0.baidu.com/it/u=1898016897,158304709&fm=253&fmt=auto&app=138&f=JPEG?w=500&h=889',
						title: '即将举行 | 10月10日-25日 天机时间'
					}
				]
			}
		},
		onLoad() {

		},
		methods: {

		}
	}
</script>

<style>
	
</style>
