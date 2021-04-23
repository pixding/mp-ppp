<script lang="ts">
import Vue from 'vue';
export default Vue.extend({
  mpType: 'app',
  onLaunch() {
    console.log('App Launch');
  },
  onShow() {
    console.log('App Show');
  },
  onHide() {
    console.log('App Hide');
  },
});
</script>

<style>
view,
cover-view {
  box-sizing: border-box;
  font-family: 'FZY4JW', 'PingFang SC', sans-serif;
}

view[hidden],
image[hidden] {
  display: none !important;
}

page {
  font-family: 'PingFang SC', sans-serif;
  font-size: 28rpx;
  line-height: 1.5;
  color: #202b43;
}
</style>
