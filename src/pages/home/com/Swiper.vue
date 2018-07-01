<template>
	<div class="wiper">
		<swiper :options="swiperOption">
		    <swiper-slide v-for="item of swiperList" :key='item.id'>
		    	<img  class='swiper-img' :src="item.imgUrl"/>
		    </swiper-slide>
		    <div class="swiper-pagination"  slot="pagination"></div>
	  	</swiper>
	</div>
</template>

<script>
	export default{
		name:'HomeSwiper',
		data(){
			return{
				swiperOption:{
					pagination:'.swiper-pagination',
					loop:true
				},
				swiperList:[{
					id:'001',
					imgUrl:'http://img1.qunarzz.com/piao/fusion/1806/2e/951884b5db2e02.jpg_750x200_3fb1ea7d.jpg'
				},{
					id:'002',
					imgUrl:'http://img1.qunarzz.com/piao/fusion/1804/c4/1cdd28811593b802.jpg_750x200_5fbb7c91.jpg'
				}]
			}
		}
	}
</script>

<style lang="scss" scoped>
.wiper{
	height:100px;
	background: #eeee;	
	.swiper-img{
		width:100%
	}
}

</style>