<template>
  <div class="opera">
    <div class="opera-top"></div>
  </div>
</template>

<script>
export default {
  name: 'OperaLogo'
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .opera{
    width: 258px;
    height: 275px;
    background: #F22629;
    border-radius: 258px 258px 258px 258px /275px 275px 275px 275px;
    position: relative;
  }

  .opera-top{
    width: 112px;
    height: 231px;
    background: #fff;
    border-radius: 112px 112px 112px 112px /231px 231px 231px 231px;
    position: absolute;
    left: 50%;
    right: 50%;
    top: 50%;
    bottom: 50px;
    margin-left: -56px;
    margin-top: -115px;
  }
</style>
