<template>
  <view class="page-mdppp">
    <view class="game-week">时间：00/52</view>
    <view class="game-main">
      <view class="game-market">
        <view class="tb-bread">
          <view class="title"
            ><image src="@/static/icon/market.svg" class="icon" />Market</view
          >
        </view>
        <view class="tb-header">
          <view class="h-name">货物</view>
          <view>价格</view>
        </view>
        <view class="tb-body" v-for="(item, index) in 5" :key="index">
          <view class="p-name">特斯拉</view>
          <view class="p-price">100,000</view>
        </view>
      </view>
      <view class="game-warehourse">
        <view class="tb-bread">
          <view class="title"
            ><image
              class="icon"
              src="@/static/icon/warehouse.svg"
            />Warehouse</view
          >
          <view class="capacity">0/200</view>
        </view>
        <view class="tb-header">
          <view class="h-name">货物</view>
          <view>价格</view>
          <view>数量</view>
        </view>
        <view class="tb-body" v-for="(item, index) in 3" :key="index">
          <view class="p-name warehourse">特斯拉</view>
          <view class="p-price">10</view>
          <view class="p-num">1</view>
        </view>
      </view>
    </view>

    <view class="game-user-profile">
      <view class="profile">
        <image src="@/static/icon/health.svg" class="icon" />
        <text class="txt">Health</text>
        <view
          :style="{ width: 200 + 'rpx', height: '36rpx' }"
          class="score"
        ></view>
      </view>
      <view class="profile">
        <image src="@/static/icon/reputation.svg" class="icon" />
        <text class="txt">Fame</text>
        <view
          :style="{ width: '210rpx', height: '36rpx' }"
          class="score"
        ></view>
      </view>
    </view>

    <view class="game-trade">
      <view class="user-amount"
        ><image src="@/static/icon/finance.svg" class="icon" />
        100,000,000,000</view
      >

      <view class="trade-prod">
        <view class="trade-item">特斯拉</view>
        <view class="trade-val">
          <slider
            value="100"
            @change="sliderChange"
            min="50"
            max="200"
            show-value
          />
        </view>
      </view>
      <view>
        <view>花费：100,000,000</view>
        <view>
          <view>取消</view>
          <view>确认</view>
        </view>
      </view>
    </view>
  </view>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';

@Component({
  components: {},
})
export default class Sale extends Vue {
  x = 100;
  onLoad() {}
}
</script>

<style lang="less" scoped>
.page-mdppp {
  .game-week {
    height: 80rpx;
    line-height: 80rpx;
    background: #857ceb;
    text-align: right;
    padding: 0 20rpx;
    color: #fff;
    font-size: 28rpx;
    margin-bottom: 20rpx;
  }

  .game-main {
    border-top: 4rpx solid #000;
    border-bottom: 4rpx solid #000;
    height: 500rpx;
    display: flex;
    justify-content: space-between;
    font-size: 28rpx;

    .game-market {
      width: 300rpx;
      border-right: 4rpx solid #000;
      background: #f6fff9;
      padding: 20rpx;
    }
    .game-warehourse {
      width: 446rpx;
      background: #f4f7ff;
      padding: 20rpx;
    }

    .tb-bread {
      display: flex;
      font-size: 24rpx;
      justify-content: space-between;
      align-items: center;
      height: 30rpx;
      line-height: 30rpx;
      margin-bottom: 30rpx;
      .title {
        display: flex;
        align-items: center;
        .icon {
          width: 32rpx;
          height: 26rpx;
          margin-right: 8rpx;
        }
      }
      .capacity {
        color: #f24981;
        font-weight: bold;
      }
    }

    .tb-header {
      display: flex;
      justify-content: space-between;
      margin-bottom: 20rpx;
      .h-name {
        flex-basis: 144rpx;
        text-align: center;
      }
    }

    .tb-body {
      margin-bottom: 20rpx;
      display: flex;
      justify-content: space-between;
      align-items: center;
      .p-name {
        width: 160rpx;
        height: 48rpx;
        flex-grow: 0;
        background: #1a2a4a;
        text-align: center;
        color: #fff;
        font-size: 24rpx;
        line-height: 48rpx;
        border-radius: 24rpx;
        &.warehourse {
          background: #ed6761;
        }
      }
      .p-price {
        flex-shrink: 1;
        flex-basis: 160rpx;
        text-align: right;
      }
      .p-num {
        flex-shrink: 1;
        flex-basis: 160rpx;
        text-align: right;
      }
    }
  }

  .game-user-profile {
    background: #f2fdfd;
    border-bottom: 4rpx solid #000;
    height: 88rpx;
    display: flex;
    align-items: center;
    padding: 20rpx;
    margin-bottom: 20rpx;
    .profile {
      flex-grow: 0;
      flex-basis: 355rpx;
      display: flex;
      align-items: baseline;

      .icon {
        width: 48rpx;
        height: 48rpx;
        margin-right: 8rpx;
      }
      .txt {
        font-size: 20rpx;
        margin-right: 8rpx;
      }
      .score {
        display: flex;
        background: url('@/static/icon/star.png') no-repeat;
        background-size: cover;
      }
    }
  }

  .game-trade {
    background: #f2fdfd;
    padding: 20rpx;
    .user-amount {
      height: 60rpx;
      line-height: 60rpx;
      color: #ed6f2d;
      display: flex;
      justify-content: flex-start;
      align-items: center;
      font-size: 32rpx;
      margin-bottom: 20rpx;
      .icon {
        width: 50rpx;
        height: 50rpx;
        margin-right: 10rpx;
      }
    }

    .trade-prod {
      padding: 10rpx 0;
      display: flex;
      align-items: center;

      .trade-item {
        flex-basis: 120rpx;
        text-align: left;
      }
      .trade-val {
        flex-grow: 1;
      }
    }
  }
}
</style>
