<template>
	<div class="two">
		<div id="pic">

		</div>
	</div>
</template>

<script>
	import echarts from 'echarts';
	import 'echarts/map/js/china';
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
				var myChart = echarts.init(document.getElementById('pic'));
				var geoCoordMap = {};
				var map1 = [ {
            "name":"山东",
            "value":0
        },
        {
            "name":"浙江",
            "value":0
        },
        {
            "name":"湖北",
            "value":50
        },
        {
            "name":"安徽",
            "value":0
        },
        {
            "name":"上海",
            "value":23
        },
        {
            "name":"云南",
            "value":0
        },
        {
            "name":"陕西",
            "value":0
        },
        {
            "name":"广西",
            "value":0
        },
        {
            "name":"湖南",
            "value":0
        },
        {
            "name":"河南",
            "value":0
        },
        {
            "name":"福建",
            "value":0
        },
        {
            "name":"四川",
            "value":0
        },
        {
            "name":"贵州",
            "value":0
        },
        {
            "name":"河北",
            "value":0
        },
        {
            "name":"北京",
            "value":23
        },
        {
            "name":"广东",
            "value":10
        },
        {
            "name":"宁夏",
            "value":0
        },
        {
            "name":"江西",
            "value":0
        },
        {
            "name":"江苏",
            "value":0
        },
        {
            "name":"山西",
            "value":0
        },
        {
            "name":"重庆",
            "value":0
        },
        {
            "name":"辽宁",
            "value":0
        },
        {
            "name":"黑龙江",
            "value":0
        },
        {
            "name":"内蒙古",
            "value":0
        },
        {
            "name":"甘肃",
            "value":0
        },
        {
            "name":"海南",
            "value":0
        },
        {
            "name":"吉林",
            "value":0
        },
        {
            "name":"天津",
            "value":0
        },
        {
            "name":"新疆",
            "value":0
        },
        {
            "name":"青海",
            "value":0
        },
        {
            "name":"西藏",
            "value":0
        }
				];
				var data1 = [{
					name: '湖北',
					value: 50
				}, {
					name: '上海',
					value: 23
				}, {
					name: '广东',
					value: 10
				}, {
					name: '北京',
					value: 23
				},
				];
				var mapFeatures = echarts.getMap('china').geoJson.features;
				mapFeatures.forEach(function(v) {
					// 地区名称
					var name = v.properties.name;
					// 地区经纬度
					geoCoordMap[name] = v.properties.cp;
				});
				var convertData = function(data1) {
					var res = [];
					for(var i = 0; i < data1.length; i++) {
						var geoCoord = geoCoordMap[data1[i].name];
						if(geoCoord) {
							res.push({
								name: data1[i].name,
								value: geoCoord.concat(data1[i].value),
							});
						}
					}
					return res;
				};
				//取出最大值和最小值
				let va = [];
				for(let i = 0; i < map1.length; i++) {
					va.push(map1[i].value);
				};
				let max = Math.max.apply(null, va);
				let min = Math.min.apply(null, va);
				// 指定图表的配置项和数据
				var option = {
					//标题组件，包含主标题和副标题。
					title: [{
							text: "好友分布图",
							x: 'center',
							top: 'top',
							textStyle: {
								color: "#dddddd",
								fontFamily: '等线',
								fontSize: 14,
							},
						},

					],
					tooltip: {
						trigger: 'item',
						formatter: function(params) {
							// console.log(params);
							var toolTiphtml = "";
							if(params.seriesIndex == 0 && params.data != undefined) {
								//鼠标在地图并且有数据
								toolTiphtml = params.name + "有" + params.value+'位好友';
								return toolTiphtml;
							} else if(params.seriesIndex == 1) {
								//在小圆点
								toolTiphtml = params.name + "有" + params.value[2]+'位好友';
								return toolTiphtml;
							} else if(params.seriesIndex == 2) {
								//鼠标在气泡
								toolTiphtml = params.name + '有' + params.value[2] + "位好友";
								return toolTiphtml;
							} else {
								return; //南海诸岛
							}

						}
					},
					visualMap: {
						show: true,
						min: min,
						max: max,
						precision: 0,
						left: 'left',
						top: 'bottom',
						text: ['高', '低'], // 文本，默认为数值文本
						calculable: true,
						seriesIndex: [0],
						inRange: {
							// color: ['#3B5077', '#031525'] // 蓝黑
							// color: ['#ffc0cb', '#800080'] // 红紫
							// color: ['#3C3B3F', '#605C3C'] // 黑绿
							// color: ['#0f0c29', '#302b63', '#24243e'] // 黑紫黑
							// color: ['#23074d', '#cc5333'] // 紫红
							// color: ['#00467F', '#A5CC82'] // 蓝绿
							color: ['#009DFF', '#51BBB8', '#D1EB47', '#FFC126', '#FF7C2F']

						}
					},
					geo: {
						show: true,
						map: 'china',
						label: {
							normal: {
								show: false
							},
							emphasis: {
								show: false,
							}
						},
						roam: true,
						itemStyle: {
							normal: {
								areaColor: '#031525',   //地区背景色
								borderColor: '#2B91B7', //地图边框
							},
							emphasis: {
								areaColor: '#2B91B7',
							}
						}
					},
					series: [{
							name: '地图',
							type: 'map',
							map: 'china',
							geoIndex: 0,
							aspectScale: 0.75, //长宽比
							showLegendSymbol: false, // 存在legend时显示
							label: {
								normal: {
									show: true
								},
								emphasis: {
									show: false,
									textStyle: {
										color: '#26ff29'
									}
								}
							},
							roam: true,
							itemStyle: {
								normal: {
									areaColor: '#EEEEEE',
									borderColor: '#EEEEEE',
								},
								emphasis: {
									areaColor: '#EEEEEE'
								}
							},
							animation: false,
							data: map1
						},
						{
							name: '小园点',
							type: 'scatter',
							coordinateSystem: 'geo',
							zlevel: 3,
							data: convertData(map1),
							symbolSize: 5,
							label: {
								normal: {
									show: true,
									position: 'right',
									formatter: '{b}',
									emphasis: {
										show: true
									}
								}
							},
							itemStyle: {
								normal: {
									color: '#EEEEEE'
								}
							}
						},
						{
							name: '气泡',
							type: 'scatter',
							coordinateSystem: 'geo',
							symbol: 'pin', //气泡
							symbolSize: 50,
							label: {
								normal: {
									formatter: function(params) {
										return params.data.value[2];
									},

									show: true,
									textStyle: {
										color: '#fff',
										fontSize: 9,
									}
								}
							},
							itemStyle: {
								normal: {
									color: '#e2787c', //标志颜色
								}
							},
							zlevel: 6,
							data: convertData(data1),
						},
					]
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
	.two {
		width: 100%;
		height: 500px;
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
