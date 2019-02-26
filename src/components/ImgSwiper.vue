<template>
  <div class="swiper">
    <swiper class="swiper-container" next-margin="50rpx" previous-margin="50rpx" v-if="imgUrls.length > 0" indidator-dots="imgUrls.length > 1" circular="true">
      <block v-for="(item, index) in imgUrls" :key="index" >
        <swiper-item class="swiper-item">
          <image :src="item" mode="widthFix"> </image>
        </swiper-item>
      </block>
    </swiper>
  </div>
</template>

<script>
export default {
  data() {
    return {
      showAddress: false
    };
  },
  props: {
    imgUrls: Array,
    activityImgs:Array,
    lateNewsImgUrls:Array
  },
  mounted (){
    console.log(this.imgUrls)
  },
  methods: {
    showAddressView() {
      this.showAddress = !this.showAddress;
    }
  }
};
</script>

<style lang="scss" scoped>
.swiper {
  width: 100%;
  height: 500rpx;
  .backImg {
    width: 100%;
  }
  .swiper-container {
    height: 470rpx;
    display: flex;
    .swiper-item {
      image {
        width: 600rpx;
        // height: 600rpx;
      }
    }
  }
}
</style>
