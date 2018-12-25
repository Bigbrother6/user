<template>
  <div class="five">
    <h4>项目经验</h4>
    <p>项目名称:睿达控风控数据分析平台</p>
    <p>项目链接: <a href="http://www.ruidakong.com" target="_blank">www.ruidakong.com</a> </p>
    <p>开发技术:html5,css3,javascript,vue,element-ui,echarts</p>
    <p>项目描述:可以查询到公司信息，通过对债券、地区风险、企业关系图谱、风险预警、企业画像、舆情信息等模块的分析判断目前的一个企业状况</p>
    <p>实现过程</p>
    <ul>
      <li>1.采用前后端分离开发模式,前端实现页面和功能交互，后台提供数据接口。</li>
      <li>2.前端使用vue框架，使用webpack打包部署。</li>
      <li>3.使用vue-axios调用后台数据显示在页面</li>
      <li>4.使用Echarsts地图，柱状图，折现图，扇形图，雷达图，关系图，实现数据可视化</li>

    </ul>
  </div>
</template>

<script>
  export default {
    name: 'two',
    data() {
      return {
        msg:"",
      }
    },
    mounted() {

    },
    methods:{}
  }
</script>
<style scoped>
  .five {
    width: 100%;
    height: 400px;
    color: #EEEEEE;
    border: 30px solid #4a444400;
    -o-border-image: url("../assets/1.png") 30 30 stretch;
    border-image: url("../assets/1.png") 30 30 stretch;
  }

  #pic {
    width: 100%;
    height: 100%;
    text-align: center;
  }
</style>

