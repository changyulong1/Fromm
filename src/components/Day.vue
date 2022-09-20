<template>
  <div>
    <p> <span v-if="show1">*</span>{{ text }}</p>
    <div class="select">
      <van-cell  @click="showPopup">{{ value || "选择器" }}<van-icon v-if="!value" name="arrow-down" /></van-cell>
      <van-popup  position="bottom" v-model="show">
        <div class="gre"><span>年</span><span>月</span><span>日</span></div>
        <van-datetime-picker
            v-model="currentDate"
            type="date"
            :min-date="minDate"
            :max-date="maxDate"
            @confirm="onConfirm"
            @cancel="onCancel"
            :value-key="value"
        >
        </van-datetime-picker>
      </van-popup>
    </div>
  </div>
</template>

<script lang="ts">
import dayjs from 'dayjs'
export default {
  name: "Day",
  props:['text','show1'],
  data(){
    return {
      show:false,
      value:null,
      minDate: new Date(2020, 0, 1),
      maxDate: new Date(2025, 10, 1),
      currentDate: new Date(2021, 0, 17),
    }
  },

  methods: {
    showPopup() {
      this.show = true;
    },
    onConfirm(value) {
      this.show = false;
      this.value = dayjs(value).format('YYYY年MM月DD日')
    },
    onCancel() {
      this.show = false;
    },
  },
};
</script>

<style lang="scss">
div{
    p {
      margin-top: 10px;
      text-align: left;
      spna{
        color: red;
      }
    }
  .select {
    margin: 10px 10px 20px 10px;
    text-align: center;
    border: 1px solid #000000;
    .van-cell__value{
      text-align: center;
      width: 100%;
      span{
        display: inline-block;
        margin-left: 10px;
      }
    }
    .van-popup{
      .gre{
        background: #efefef;
        display: flex;
        position: absolute;
        z-index:2;
        top: 40px;
        width: 100%;
        padding: 4px 0;
        border-top: 1px solid #c2c2c2;
        border-bottom: 1px solid #c2c2c2;
        span{
          flex: 1;
          text-align: center;
        }
      }
      .van-picker>.van-picker__toolbar{
        padding: 10px;
        background: #ffffff;
        .van-picker__cancel{
          background: #ffffff;
          border: 1px solid #c2c2c2;
          border-radius: 4px;
        }
        .van-picker__confirm{
          background-color: #0677f9;
          color: #ffffff;
          border-radius: 4px;
        }
      }
    }
  }
}


.van-picker__columns{
  .van-picker__mask{
    background-image:none;
  }
  .van-picker-column{
    background: #ccc;
    .van-picker-column__wrapper{
      background: #ccc;
      .van-picker-column__item{
        color: #8f8f8f;
        &.van-picker-column__item--selected{
          color:#000000;
        }
      }
    }
  }
  .van-picker__frame{
    left: 0;
    right: 0;
    border-top:1px solid #c2c2c2;
    border-bottom:1px solid #c2c2c2;
  }
}
</style>
