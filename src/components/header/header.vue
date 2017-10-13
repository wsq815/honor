<template>
	<div class="header">
		<div class="content-wrapper">		
			<div class="avatar">
				<img width="64" height="64" :src="seller.avatar" alt="">
			</div>
			<div class="content">
				<div class="title">
					<i class="brand"></i>
					<span class="name">{{seller.name}}</span>
				</div>
				<div class="desc">
					{{seller.description}} / {{seller.deliveryTime}}分钟送达
				</div>
				<div class="support">
					<i></i>
					<span class="text">{{seller.supports[0].description}}</span>
				</div>
			</div>
		</div>
	</div>
</template>

<script>
	export default {
		props: {
			seller: {
				type: Object
			}
		},
		created() {
			
		}
	}
</script>

<style rel="stylesheet/scss" lang="scss">
	@import '../../common/scss/mixin.scss';

	.content-wrapper{
		background: #000;
		padding: 24px 24px 18px 24px;
		font-size: 0;
		.avatar{
			display: inline-block;
			vertical-align: top;
		}
		.content{
			display: inline-block;
			vertical-align: top;
			margin-left: 16px;
			.title{
				margin-top: 2px;
				.brand{
					@include bg-image("brand");
				}
				.name{
					line-height: 16px;
					font-size: 16px;
					color:#fff;
					font-weight: bold;
				}
			}
			.desc{
				line-height: 12px;
				margin-top: 8px;
				font-size: 12px;
				color: #fff;
			}
			.support{
				margin-top: 10px;
				.text{
					line-height: 12px;
					font-size: 10px;
					color: #fff;
				}
			}
		}
	}
</style>