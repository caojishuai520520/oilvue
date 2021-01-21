<template>
  <div class="number-card">
    <div class="item">
      <span>销售总收入</span>
      <div class="money">
        <span class="text">{{ money}}</span>
		<span class="unte">元</span>
		
      </div>
      <div class="info"><span>周同比 </span><span>降56.65%</span></div>
      <a-popover title="销售总收入" overlayClassName="note">
        <template slot="content">
          <div class="">
            <p>销售总收入：今天截止此时的销售总收入周同比：与上周同一天截止此时的销售总收入对比</p>
            <span>注：此数据实时更新</span>
          </div>
        </template>
        <span class="anticon">i</span>
      </a-popover>
    </div>
  </div>
</template>

<script>
import IconSelector from '@/components/IconSelector'

export default {
  components: { IconSelector },
  data() {
    return {
      money: '14971.22',
      data: [],
    }
  },
  methods: {},
}
</script>

<style lang="scss">
.item {
  flex: 1;
  height: 150px;
  display: flex;
  margin: 8px 10px;
  position: relative;
  flex-direction: column;
  justify-content: space-between;
  box-shadow: 0 0 6px 0 rgba(0, 0, 0, 0.1);

  .money {
    display: flex;
    align-items: flex-end;
    justify-content: center;

    .text {
      font-size: 30px;
	  color: #1e1e28;
	  line-height: 34px;
	  margin-right: 5px;
    }

  }

  > span:not(.anticon) {
    margin-top: 20px;
    font-size: 14px;
    color: #3c3c46;
    letter-spacing: 0;
    line-height: 14px;
    text-align: center;
  }

  .info {
    height: 16px;
    margin-left: 10px;
    margin-bottom: 10px;
    justify-content: flex-start;

    > span {
      font-size: 12px;
      color: #3c3c46;
    }
  }

  .anticon {
    position: absolute;
    top: 10px;
    right: 10px;
    cursor: pointer;
  }
}

// 卡片类名
.note {
  width: 350px;
}
</style>
