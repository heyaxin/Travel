<template>
	<div>
		<home-header></home-header>
		<home-swiper :list="swiperList"></home-swiper>
		<home-icons :list="iconList"></home-icons>
		<home-recommend :list="recommendList"></home-recommend>
		<home-weekend :list="weekendList"></home-weekend>

	</div>
</template>

<script>
import HomeHeader from './com/Header'
import HomeSwiper from './com/Swiper'
import HomeIcons from './com/Icons'
import HomeRecommend from './com/Recommend'
import HomeWeekend from './com/Weekend'
import axios from 'axios'
export default{
	name:"Home",
	components:{
		HomeHeader,
		HomeSwiper,
		HomeIcons,
		HomeRecommend,
		HomeWeekend
	},
	data () {
		return {
			swiperList: [],
			iconList: [],
			recommendList: [],
			weekendList: []
		}
	},
	methods: {
		getHomeInfo () {
			axios.get('/api/index.json')
			.then(this.getHomeInfoSucc)
		},
		getHomeInfoSucc (res) {
			var res = res.data;
			if (res.ret && res.data) {
				const data = res.data
				this.swiperList = data.swiperList
				this.iconList = data.iconList
				this.recommendList = data.recommendList
				this.weekendList = data.weekendList
			}
		}
	},
	mounted () {
		this.getHomeInfo()
	}
}
</script>

<style>
</style>