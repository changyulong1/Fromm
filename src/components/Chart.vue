<template>
  <div>
    <p><span v-if="show">*</span> {{ text }}</p>
    <table>
      <tr>
        <th>{{text1 }}</th>
        <th>{{text2 }}</th>
        <th>{{text3 }}</th>
        <th>{{text4}}</th>
      </tr>
      <tr>
        <td><input type="text"></td>
        <td><input type="text"></td>
        <td><input type="text"></td>
        <td><input type="text"></td>
      </tr>
      <tr>
        <td><input type="text"></td>
        <td><input type="text"></td>
        <td><input type="text"></td>
        <td><input type="text"></td>
      </tr>
      <tr class="last">
        <td><input type="text"></td>
        <td><input type="text"></td>
        <td><input type="text"></td>
        <td><input type="text"></td>
      </tr>
    </table>
  </div>
</template>

<script lang="ts">
export default {
  name: "Chart",
  props:['show','text','text1','text2','text3','text4']
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
  table{
    margin-top: 10px;
    padding-right: 10px;
    tr {
      display: flex;
      th{
        flex: 1;
        border-top: 1px solid #000;
        border-bottom: 1px solid #000;
        border-right: 1px solid #000000;
        padding: 4px 0;
        font-size: 12px;
        &:first-child{
          border-left: 1px solid red;
          border-top-left-radius: 8px;
        }
        &:last-child{
          border-top-right-radius: 8px;
        }
      }
      td{
        flex: 1;
        border-bottom: 1px solid #000000;
        border-right: 1px solid #000000;
        padding: 4px 0;
        &:first-child{
          border-left: 1px solid #000000;
        }
        input{
          width: 100%;
          border: none;
        }
      }
      &.list{
        td:first-child,td:first-child>input{
          border-bottom-left-radius: 8px;
        }
        td:first-child,{
          position: relative;
          input{
            position: relative;
          }
        }

      }

    }
  }
}

</style>
