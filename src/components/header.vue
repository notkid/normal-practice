<template>
	<header>
		<section class="logoPart">
			<section class="goback">
				<svg fill="#fff"> 
					<use xmlns:xlink="http://www.w3.org/1999/xlink" xlink:href="#back"></use>
				</svg>
			</section>
			<section class="wall">|</section>
			<!-- <slot name='clickrefresh' ></slot> -->
			<section class="covers_name">
				<span class="ellipsis">
					某某人
				</span>
			</section>
		</section>
	</header>	
</template>

<script>

	export default{
		data(){
			return{}
		}
	}
</script>
<style lang="less" scoped>
@import '../style/index';
    
	header{
		.widthHeight(100%,2.06933em);
		background:#5293CF;
		z-index:200;
		color:#fff;
		position: fixed;
		.logoPart{
			.topcenter;
			.sizeColor(0.704rem,#fff);
			left:0.5973333333rem;
			.justify(flex-start);
			align-items:center;
			.goback{
				.widthHeight(1rem,1rem);
				svg{
					.widthHeight(100%,100%);
				}
			}
			.wall{
				margin:0 0.5333333333rem;
				.sizeColor(1.0666666667rem,#5293CF);
			}
			
			.covers_name{
				span{
					.sizeColor(0.704rem,#fff);
					display:block;
					width:9.5rem;
				}
			}
		}
	}
</style>