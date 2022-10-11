# swiper-card
 卡片类型的广告展示组件，适用于移动端（Card type AD display component for mobile）
 gitHub地址`https://github.com/duanwei1273/swiper-card.git`
 npm地址`https://www.npmjs.com/package/swiper-card`
### npm加载（推荐）
##### 安装
```
npm i swiper-card
```
##### 导出
```
import compSwiper from 'swiper-card'
```
### 直接引入
请复制comm-swiper-card/components目录下comp-swiper.vue文件到你的项目中
##### 导出使用,复制下方
```
import compSwiper from '@/components/comp-swiper.vue'
```

### 传入值
```
<comp-swiper :cardDatas="cardList" />
```
##### 值的结构
```
cardList: [
						{
							id: 1,
							src: 'imageSrc',
						},
						{
							id: 2,
							src: 'imageSrc5',
						},
						{
							id: 3,
							src: 'imageSrc',
						}
					]
```


