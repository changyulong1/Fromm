<template>
<div>
  <p><span v-if="!show">*</span> {{ text }}</p>
  <textarea name="" id="" cols="30" rows="8" placeholder="请输入"></textarea>
</div>
</template>

<script lang="ts">
export default {
  name: "Textatrs",
  props:['text','show']
};
</script>

<style lang="scss" scoped>
div{
  p{
    margin-top: 10px;
    text-align: left;
    span{
      color: red;
    }
  }
  textarea {
    width: 100%;
    border: none;
    padding: 16px 0;
    border-bottom: 1px solid #ccc;
  }
}

</style>
