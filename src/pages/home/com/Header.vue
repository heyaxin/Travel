<template>
<div>
	<div class="header">
		<div class="header-left">
			<div class="iconfont back-icon">&#xe600;</div>
		</div>
		<div class="header-input">
			<span class="iconfont">&#xe6e4;</span>
			输入城市/景点/游玩主题
		</div>
		<router-link to="/city">
			<div class="header-right">
				{{this.$store.state.city}}
				<span class="iconfont arrow-icon">&#xe64a;</span>
			</div>
		</router-link>
	</div>
</div>
</template>

<script>
	export default{
		name:'HomeHeader',
		props: {
			city: String
		}
	}
</script>

<style lang='scss' scoped="scoped">
@import '~styles/varible.scss';
.header{
	line-height: $headerHeight;
	display:flex;
	background:$bgColor;
	color:#fff;
	
	.header-left{
		width: 0.64rem;
		float:left;
		.back-icon{
			text-align: center;
			font-size:.4rem;
		}
	}
	.header-input{
		flex:1;
		height:.64rem;
		margin-top: .12rem;
		margin-left:.2rem;
		background: #fff;
		padding-left: .2rem;
		border-radius: 0.1rem;
		line-height: .64rem;
		color: #ccc;
	}
	.header-right{
		width: 1.24rem;
		float:right;
		text-align: center;
		color:#fff;
		.arrow-icon{
			font-size:.24rem;
			margin-left: -0.04rem;
		}
	}
}
</style>