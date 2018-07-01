<template>
	<div>
		<home-header></home-header>
		<home-swiper></home-swiper>
		<home-icons></home-icons>
	</div>
</template>

<script>
import HomeHeader from './com/Header'
import HomeSwiper from './com/Swiper'
import HomeIcons from './com/Icons'
export default{
	name:"Home",
	components:{
		HomeHeader,
		HomeSwiper,
		HomeIcons
	}
}
</script>

<style>
</style>