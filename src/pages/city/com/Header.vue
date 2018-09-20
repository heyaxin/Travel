<template>
    <div class="header">
      城市选择
      <router-link to="/">
        <div class="iconfont header-back">&#xe600;</div>
      </router-link>
    </div>
</template>

<script>
export default {
    name: 'CityHeader'
}
</script>

<style lang="scss" scoped>
@import '~styles/varible.scss';
 .header {
    position: relative;
    background: $bgColor;
    color:#ffffff;
    text-align: center;
    overflow: hidden;
    height: $headerHeight;
    line-height: $headerHeight;
    .header-back {
        top:0;
        left:0;
        position: absolute;
        width: 0.64em;
        text-align: center;
        font-size: .4rem;
        color:#ffffff;
    }
}
</style>
