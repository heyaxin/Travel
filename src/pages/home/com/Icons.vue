<template>
	<div class="icons">
		<swiper>
			<swiper-slide v-for='_item,index in pages' :key='index'>
				<div class="icon" v-for="item in _item" :key='item.id'>
					<div class="icon-img">
						<img class='icon-img-countent' :src='item.imgUrl'/>
					</div>
					<p class="icon-desc">{{item.keywords}}</p>
				</div>
			</swiper-slide>
		</swiper>
	</div>
</template>

<script>
	export default{
		name:'HomeIcons',
		data(){
			return{
				iconList:[{
					id:'001',
					imgUrl:'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
					keywords:'景点门票'
				},{
					id:'002',
					imgUrl:'http://img1.qunarzz.com/piao/fusion/1804/ff/fdf170ee89594b02.png',
					keywords:'必有榜单'
				},{
					id:'003',
					imgUrl:'http://img1.qunarzz.com/piao/fusion/1803/3e/86314b2af03b7502.png',
					keywords:'水上玩乐'
				},{
					id:'004',
					imgUrl:'http://img1.qunarzz.com/piao/fusion/1804/5a/13ceb38dcf262f02.png',
					keywords:'一日游'
				},{
					id:'005',
					imgUrl:'http://img1.qunarzz.com/piao/fusion/1803/20/831d62d2e1c7be02.png',
					keywords:'名胜古迹'
				},{
					id:'006',
					imgUrl:'http://img1.qunarzz.com/piao/fusion/1803/c1/6f15f887179fa002.png',
					keywords:'夫子庙'
				},{
					id:'007',
					imgUrl:'http://img1.qunarzz.com/piao/fusion/1803/fa/2548667cb6e902.png',
					keywords:'总统府'
				},{
					id:'008',
					imgUrl:'http://img1.qunarzz.com/piao/fusion/1803/97/02f5043b51b2102.png',
					keywords:'牛首山'
				},{
					id:'009',
					imgUrl:'http://img1.qunarzz.com/piao/fusion/1803/95/8246f27355943202.png',
					keywords:'万达主题乐园'
				},{
					id:'010',
					imgUrl:'http://img1.qunarzz.com/piao/fusion/1803/20/831d62d2e1c7be02.png',
					keywords:'中山陵'
				}]
			}
		},
		computed:{
			pages(){
				const pages=[],
				PageNum=Math.ceil(this.iconList.length/8);
				for(var i=0;i<PageNum;i++){
					pages[i]=this.iconList.slice(i*8,i*8+8);
					
				}
				return pages
				
				
			}

		}
	}
</script>

<style lang='scss' scoped>
@import '~styles/varible.scss';
.icons{
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