<template>
  <div>
    <p><span v-if="show1">*</span>{{text }}</p>
    <div class="select">
      <van-cell  @click="showPopup">{{ value || '选择器' }}<van-icon v-if="!value" name="arrow-down" /></van-cell>
      <van-popup  position="bottom" v-model="show">
        <van-picker
            show-toolbar
            :columns="columns"
            @confirm="onConfirm"
            @cancel="onCancel"
        />
      </van-popup>
    </div>
  </div>
</template>

<script>
export default {
  name: "Gender",
  props:['text','show1'],
  data() {
    return {
      show: false,
      value:null,
      columns:["男生","女生"]
    };
  },

  methods: {
    showPopup() {
      this.show = true;
    },
    onConfirm(value){
      this.value = value
      this.show = false
    },
    onCancel(){
      this.show = false;

    },
  }
};
</script>

<style lang="scss" scoped>
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
}


</style>
