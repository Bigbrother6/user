<template>
	<div class="four">
		<p>工作经历</p>
		<p>公司名称:北京神州泰岳软件股份有限公司</p>
    <p>工作时间:2017.05--至今</p>
    <p>岗位:前端开发工程师</p>
    <p>工作内容</p>
    <ul>
     <li>1、负责WEB业务系统的前端开发，根据UI设计完成前端网页设计，并实现页面动态交互效果。</li>
      <li> 2、负责WEB业务系统页面优化和用户体验的设计；</li>
     <li>3、实现页面与后台的数据交互功能</li>
      <li>4、负责前端项目开发环境，测试环境，生产环境的打包部署上线。</li>

    </ul>
	</div>
</template>

<script>
	import echarts from 'echarts';
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
	.four {
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
