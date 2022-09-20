<template>
  <div class="warp">
    <div class="title">
      <p>杭州大连丝绸有限公司</p>
      <p>应聘登记表</p>
    </div>
    <form action="#" method="get">
      <ul>
        <li><Option :show="true" text="应聘职位"/></li>
        <li>
          <Day :show1="true"  text="填表日期"></Day>
        </li>
        <li>
          <Option :show="true" text="姓名"/>
        </li>
        <li>

          <Gender :show1="true"  text="性别"></Gender>
        </li>
        <li>
          <Day :show1="true" text="出生日期"></Day>
        </li>
        <li>
          <Option :show="true" text="民族"/>
        </li>
        <li>
          <Option :show="true" text="政治面貌"/>
        </li>
        <li>
          <Option :show="true" text="婚否"/>
        </li>
        <li>
          <Option :show="true" text="健康状况"/>
        </li>
        <li>
          <Option :show="true" text="籍贯（省、市）"/>
        </li>
        <li>
          <Option :show="true" text="联系方式"/>
        </li>
        <li>
          <Option :show="true" text="电子邮箱"/>
        </li>
        <li>
          <Option :show="true" text="学历"/>
        </li>
        <li>
          <Option :show="true" text="现住址"/>
        </li>
        <li>
          <Option :show="true" text="目前是否在职"/>
        </li>
        <li>
          <Option :show="true" text="预计到岗时间"/>
        </li>
        <li>
          <Option :show="true" text="期望薪资"/>
        </li>
        <li>
          <Option :show="true" text="外语水平"/>
        </li>
        <li>
          <Option :show="true" text="计算机水平"/>
        </li>
        <li>
          <Chart :show="true" text="教育经历（请至少完整的填写一行)" text1="时间" text2="毕业学校" text3="专业" text4="详细情况"></Chart>
        </li>
        <li>
          <Chart :show="true" text="工作经历（请至少完整的填写一行,没有则写’无‘)" text1="时间" text2="公司名称" text3="职务" text4="职责"></Chart>
        </li>
        <li>
          <Option  text="个人荣耀"/>
        </li>
        <li>
          <Option text="兴趣特长"/>
        </li>
        <li>
          <Textatrs text="自我评价"></Textatrs>
        </li>
      </ul>
      <div>
        <button>提交</button>
      </div>
    </form>
  </div>
</template>

<script>
import Option from "../components/Opiton.vue"
import Day from "../components/Day.vue"
import Gender from "../components/Gender";
import Chart from "../components/Chart";
import Textatrs from '../components/Textatrs'
export default {
  name: 'HelloWorld',
  components:{
    Chart,
    Gender,
    Option,
    Day,
    Textatrs
  },
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.warp {
  background: #ffffff;
  display: flex;
  flex-direction: column;
  /* border: 1px solid red; */
  div.title {
    padding: 10px;
    background: #7096bd;
    color: #f8eeee;
    border-bottom: 1px solid #d0dded;
    P {
      text-align: center;
    }
  }
  form {
    margin-left: 10px;
    ul>li{
      input {
        width: 100%;
        border: none;
        padding: 20px 0;
        border-bottom: 1px solid #ccc;
      }
      div{
        div.select {
          margin: 10px 0;
          text-align: center;
          margin-right: 10px;
          padding: 10px;
          border: 1px solid #ccc;
          .day{
            display: flex;
          }
          span{
            flex: 1;
            text-align: center;
            background: #cccccc;
          }
        }
        .van-cell{
          padding: 0;
          text-align: center;
          .van-icon{
            margin-left: 10px;
          }
          .van-cell__value{
            text-align: center;
          }
        }
        table {
          width: 100%;
        }
      }
    }
    &>div{
      width: 100%;
      padding-left: 10px;
      padding-right: 20px;
      display: flex;
      button {
        flex: 1;
        padding: 10px;
        border-radius: 10px;
        color: #cbe5fd;
        background: #7096bb;
        border: none;
      }
    }
  }
}
</style>
