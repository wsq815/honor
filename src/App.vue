<template>
  <div id="app">
    <v-header :seller="seller"></v-header>
    <div class="tab">
    	<router-link :to="{name:'goods'}" class="tab-item">商品</router-link>
    	<router-link :to="{name:'ratings'}" class="tab-item">评价</router-link>
    	<router-link :to="{name:'seller'}" class="tab-item">商家</router-link>
    </div>
    <div class="content">
    	<router-view></router-view>
    </div>
  </div>
</template>

<script>
import header from './components/header/header.vue'

const ERR_OK = 0
export default {
    data() {
        return {
            seller: {

            }
        }
    },
    created() {
        this.$axios.get('/api/seller').then((response) => {
            response = response.data
            if(ERR_OK === 0) {
                this.seller = response
            }
        })
        console.log(this.seller)
    },
    components: {
        'v-header': header
    }
}
</script>

<style rel="stylesheet/scss" lang="scss">
	.tab{
		display: flex;
		.tab-item{
			flex: 1;
			text-align:center;
			height: 40px;
			line-height: 40px;
			font-size: 14px;
		}
	}

</style>
