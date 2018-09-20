<template>
	<div class="icons">
		<swiper>
			<swiper-slide 
			v-for='_item,index in pages' 
			:key='index'>
				<div class="icon" v-for="item in _item" :key='item.id'>
					<div class="icon-img">
						<img class='icon-img-countent' :src='item.imgUrl'/>
					</div>
					<p class="icon-desc">{{item.desc}}</p>
				</div>
			</swiper-slide>
		</swiper>
	</div>
</template>

<script>
	export default{
		name:'HomeIcons',
		props: {
			list: Array
		},
		computed:{
			pages(){
				const pages=[],
				// this.list.forEach((item,index)=>{
				// 	const page = Math.floor(index/8)
				// 	if(!pages[page]) {
				// 		pages[page]=[]
				// 	}
				// 	pages[page].push(item)
				// })
				// return pages
				
				PageNum=Math.ceil(this.list.length/8);
				for(var i=0;i<PageNum;i++){
					pages[i]=this.list.slice(i*8,i*8+8);
					
				}
				return pages
				
				
			}

		}
	}
</script>

<style lang='scss' scoped>
@import '~styles/varible.scss';
.icons{
	margin-top: .3rem;
	padding-bottom: 50%;
	overflow: hidden;
	height: 0;
	.icon{
		position: relative;
		overflow: hidden;
		padding-bottom: 25%;
		height: 0;
		width: 25%;
		float:left;
		.icon-img{
			position: absolute;
			top:0;
			left:0;
			right:0;
			bottom:.44rem;
			padding: .1rem;
			box-sizing: border-box;
			.icon-img-countent{
				display: block;
				margin:0 auto;
				height: 100%;
			}
		}
		.icon-desc{
			position: absolute;
			left:0;
			right:0;
			bottom:0;
			line-height:.44rem;
			height: .44rem;
			color:$darkTextColor;
			text-align: center;
		}
	}
}
</style>

<style lang="scss">
	.icons .swiper-container{
		padding-bottom: 50%;
		height: 0;
	}
</style>