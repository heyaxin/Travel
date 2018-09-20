<template>
    <div class="list" ref="wrapper">
      <div>
         <div class="area">
             <div class="title border-topbottom">当前城市</div>
                <div class="button-list">
                    <div class="button-wrapper">
                        <div class="button">{{this.$store.state.city}}</div>
                    </div>
                </div>
           </div>
            <div class="area">
                <div class="title border-topbottom">热门城市</div>
                <div class="button-list">
                    <div 
                    class="button-wrapper"
                     v-for="item in hot"
                     :key="item.id"
                     @click="handleCityClick(item.name)"
                     >
                        <div class="button">{{item.name}}</div>
                    </div>
                </div>
            </div>
            <div class="area" v-for="(item,key) in cities" :key = "key">
                <div class="title border-topbottom">{{key}}</div>
                <div class="item-list">
                    <div class="item">
                        <div 
                        class="item border-bottom"
                        v-for="innerItem in item"
                        :key = "innerItem.id"
                         @click="handleCityClick(innerItem.name)"
                        >
                        {{innerItem.name}}</div>
                    </div>
                </div>
            </div>
     </div>   
    </div>
</template>

<script>
import BScroll from 'better-scroll'
export default {
    name:'CityList',
    props: {
        hot: Array,
        cities: Object
    },
    methods: {
        handleCityClick(city) {
            this.$store.commit('changeCity',city)
            this.$router.push('/')
        }
    },
    mounted () {
        this.scroll = new BScroll(this.$refs.wrapper)
    }
}
</script>

<style lang="scss" scoped>
    @import '~styles/varible.scss';
    .border-topbottom {
        &:before {
            border-color: #cccccc;
        }
        &:after {
            border-color: #cccccc;
        }
    }
     .border-bottom {
        &:before {
            border-color: #cccccc;
        }
    }
    .list{
        position: absolute;
        overflow: hidden;
        top: 1.58rem;
        bottom: 0;
        right: 0;
        left: 0;
        .title {
            line-height: .54rem;
            background: #eeeeee;
            padding-left: .2rem;
            color: #666;
            font-size: .26rem;
        }
        .button-list {
            overflow: hidden;
            padding: .1rem .6rem .1rem .1rem;
            .button-wrapper {
                width: 33.33%;
                float: left;
                .button {
                    border-radius: .06rem;
                    padding: .1rem 0;
                    text-align: center;
                    margin: .1rem;
                    border: .02rem solid #cccccc;
                }
            }
        }
    .item-list {
        .item {
            line-height: .76rem;
            padding-left: .2rem;
            color: #666;
        }
    }
}
</style>
