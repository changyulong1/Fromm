<template>
  <div class="option">
    <p><span v-if="show">*</span>{{ text }}</p>
    <input type="text" placeholder="请输入">
  </div>
</template>

<script lang="ts">
export default {
  name: "Opiton",
  props:['show','text']
};
</script>

<style lang="scss" scoped>
.option{
  display: flex;
  flex-direction: column;
  border-bottom: 1px solid #ccc;
  p{
    width: 100%;
    margin-top: 10px;
    text-align: left;
    span{
      color: red;
    }
  }
  input{
    width: 100%;
    border: none;
    padding: 20px 0;

  }
}

</style>
