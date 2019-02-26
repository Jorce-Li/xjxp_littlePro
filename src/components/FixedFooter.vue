<template>
  <footer>
    <div class="iconP">
      <i-icon type="task" size="16"/>
      <p>档期查询</p>
    </div>
    <div class="iconOrder">
      <img mode="widthFix" src="../../static/images/index/icon/icon1.png" alt="">
      <p>预约到店</p>
    </div>
    <div class="icon">
      <i-icon type="customerservice" size="20" />
    </div>
  </footer>
</template>

<script>
export default {
  data() {
    return {};
  },
  methods: {}
};
</script>

<style lang="scss" scoped>
footer{
  width: 100%;
  display: flex;
  align-items: center;
  position: fixed;
  bottom: 0;
  height: 100rpx;
  font-size: 32rpx;
  .iconP{
    width: 42%;
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    background-color: rgb(142, 124, 85);
    p{
      margin-left: 10rpx;
      color:#Fff;
    }
    img{
      width: 40rpx;
    }
  }
  .iconOrder{
    width: 42%;
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    color: rgb(251, 196, 0);
    background-color: rgb(142, 124, 85);
    p{
      margin-left: 10rpx;
    }
    img{
      width: 40rpx;
    }
  }
  .icon{
    flex: 1;
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    background-color: rgb(176, 155, 113);
    color:#fff;
  }
}
</style>
