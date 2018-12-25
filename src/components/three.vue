<template>
	<div class="three">
		<div id="pic2">

		</div>

	</div>
</template>

<script>
	import echarts from 'echarts';

	export default {
		name: 'two',
		data() {
			return {
				msg: "www"
			}
		},
		mounted() {
			this.draw();
		},
		methods: {
			draw() {
				var myChart = echarts.init(document.getElementById('pic2'));

				var data = [100, 90, 90, 90, 90,50,20]
				var titlename = ['HTML', 'CSS', 'JS', 'jquery', 'VUE','node','Angular'];
				var valdata = ['精通', '熟练', '熟练', '熟练', '熟练','熟悉',"了解"]
				var myColor = ['#22B14C', '#379AD6', '#649AA0', '#F8B448', '#56D0E3','#dddddd','#E15855'];


				var option = {
				title: [{
							text: "专业技能",
							x: 'center',
							top: 'top',
							textStyle: {
								color: "#dddddd",
								fontFamily: '等线',
								fontSize: 14,
							},
						},

					],
			    // backgroundColor: '#0e2147',
			    xAxis: {
			        show: false
			    },
			    yAxis: [{
			        show: true,
			        data: titlename,
			        inverse: true,
			        axisLine: {
			            show: false
			        },
			        splitLine: {
			            show: false
			        },
			        axisTick: {
			            show: false
			        },
			        axisLabel: {
			            color: '#fff',
			        },


			    },
				
				
				 {
			        show: true,
			        inverse: true,
			        data: valdata,
			        axisLabel: {
			            textStyle: {
			                fontSize: 12,
			                color: '#fff',
			            },
			        },
			        axisLine: {
			            show: false
			        },
			        splitLine: {
			            show: false
			        },
			        axisTick: {
			            show: false
			        },
			    }
				],
			    series: [{
			        name: '条',
			        type: 'bar',
			        yAxisIndex: 0,
			        data: data,
			        barWidth: 30,
			        itemStyle: {
			            normal: {
			                barBorderRadius: 30,
			                color: function(params) {
			                    var num = myColor.length;
			                    return myColor[params.dataIndex % num]
			                },
			            }
			        },
			        label: {
			            normal: {
			                show: true,
			                position: 'inside',
			                formatter: '{c}%'
			            }
			        },
			    }, {
			        name: '框',
			        type: 'bar',
			        yAxisIndex: 1,
			        barGap: '-100%',
			        data: [100, 100, 100, 100, 100,100,100],
			        barWidth: 40,
			        itemStyle: {
			            normal: {
			                color: 'none',
			                borderColor: '#00c1de',
			                borderWidth: 3,
			                barBorderRadius: 15,
			            }
			        }
			    }, ]
			};
				// 使用刚指定的配置项和数据显示图表。
				myChart.setOption(option);

				              //4随窗口改变自适应图表，能适应多个图
				window.addEventListener("resize",function(){
                myChart.resize();
              });
			}
		}
	}
</script>
<style scoped>
	.three {
		width:100%;
		height: 500px;
		border: 30px solid #4a444400;
		-o-border-image: url("../assets/1.png") 30 30 stretch;
		border-image: url("../assets/1.png") 30 30 stretch;
	}

	#pic2 {
		width: 100%;
		height: 100%;
		text-align: center;
	}
</style>
