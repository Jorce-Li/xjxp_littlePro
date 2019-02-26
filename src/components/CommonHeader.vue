<template>
  <header v-if="showHeader">
      <div class="headerIcon">
          <i-icon size="30" type="other" />
      </div>
      <div class="headerAddress" @click="showAddressView">
        <span>花嫁丽舍·</span>
        <span>上海</span>
        <i-icon type="packup" v-if="!showAddress" />
        <i-icon type="unfold" v-if="showAddress"/>
      </div>
      <div class="headerIM">
        <i-icon size="30" type="customerservice_fill" />
      </div>
    </header>
</template>

<script>
export default {
  data() {
    return {
      showHeader: true,
      scrollTop: 0
    };
  },
  onPageScroll(e) {
    if (e.scrollTop) {
      if (e.scrollTop - 20 > this.scrollTop) {
        this.showHeader = false;
      } else if (e.scrollTop < this.scrollTop) {
        this.showHeader = true;
      }
      this.scrollTop = e.scrollTop;
    }
  },
  methods: {
    showAddressView() {
      this.showAddress = !this.showAddress;
    }
  }
};
</script>

<style lang="scss" scoped>
header {
  position: fixed;
  top: 0;
  width: 100%;
  display: flex;
  height: 100rpx;
  border-bottom: 1px solid #ccc;
  align-items: center;
  background-color: #Fff;
  .headerIcon,
  .headerIM {
    width: 100rpx;
  }
  .headerAddress {
    flex: 1;
    display: flex;
    justify-content: center;
    align-items: center;
  }
  div {
    text-align: center;
  }
}
</style>
