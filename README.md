<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8">
    <title>ECharts</title>
    <!-- 引入 echarts.js -->
    <script type="text/javascript" src="http://echarts.baidu.com/gallery/vendors/echarts/echarts.min.js"></script>
</head>
<body>
    <!-- 为ECharts准备一个具备大小（宽高）的Dom -->
            <div id="1", style="height: 800px"></div>
	
	
			<h1 align="center">结论</h1>
			<h2 style="margin-left: 100px">晚上点击广告高峰，22：00达到峰值，但下午1点也有小高峰</h2>
			<h2 style="margin-left: 100px">用户更愿意在晚十点点击广告，但更愿意在下午一点购买，所以晚上的广告可多做宣传活动、直播推广，下午可多做促销、售卖活动</h2>
	
			<h1 align="center">疑惑</h1>
			<h2 style="margin-left: 100px">22：00比13：00的广告浏览次数高27%，但购买数量却更少</h2>
			<h2 style="margin-left: 100px">我们要如何提高种草+拔草的商业转化率，完善商业闭环？</h2>
			<h3 style="margin-left: 100px">是否因为广告、目标人群不匹配？</h2>
			<h3 style="margin-left: 100px">下午一点的广告更有哪些特点？</h2>
			<h3 style="margin-left: 100px">相比于晚10点，下午1点竞争少，广告位便宜，是否适合一些品牌的投放？</h2>
			<h3 style="margin-left: 100px">接下来我抽取了更典型的下午1点 和 晚上10点的数据特征值做特殊比对</h2>、、

            <div id="2", style="height: 800px"></div>
	            <div id="3", style="height: 800px"></div>
	            <div id="4", style="height: 800px"></div>
	            <div id="5", style="height: 800px"></div>
	            <div id="6", style="height: 800px"></div>
	            <div id="7", style="height: 800px"></div>
	            <div id="8", style="height: 800px"></div>
	           <div id="9", style="height: 800px"></div>
	            <div id="10", style="height: 800px"></div>
	            <div id="11", style="height: 800px"></div>

	


    <script type="text/javascript">
		
        var myChart = echarts.init(document.getElementById('1'));
        var option = {
    title: {
        text: '不同时间段,用户的点击率、加入购物车、喜欢、购买的次数'
    },
    tooltip: {
        trigger: 'axis',
        axisPointer: {
            type: 'cross',
            label: {
                backgroundColor: '#6a7985'
            }
        }
    },
    legend: {
        data: ['浏览','加入购物车','喜欢','购买']
    },
    toolbox: {
        feature: {
            saveAsImage: {}
        }
    },
    grid: {
        left: '3%',
        right: '4%',
        bottom: '3%',
        containLabel: true
    },
    xAxis: [
        {
            type: 'category',
            boundaryGap: false,
            data: ['00','01','02','03','04','05','06','07','08','09','10','11','12','13','14','15','16','17','18','19','20','21','22','23']
        }
    ],
    yAxis: [
        {
            type: 'value'
        }
    ],
    series: [
        {
            name: '购买',
            type: 'line',
			label: {
                normal: {
                    show: true,
                    position: 'top'
                }
            },
            data: [1304,583,290,192,113,258,716,1310,2053,2941,3928,3327,3209,3342,3208,3137,3055,2803,2498,2611,2999,3410,3282,2328]
        },	   
        {
            name: '喜欢',
            type: 'line',
			label: {
                normal: {
                    show: true,
                    position: 'top'
                }
            },
            data: [2062, 965, 521, 305, 240, 400, 913,1447,1863,2294,2782,2654,2607,2804,2696,2756,2828,2616,2306,2487,3048,3616,4046,3440]
        },
        {
            name: '加入购物车',
            type: 'line',
            label: {
                normal: {
                    show: true,
                    position: 'top'
                }
            },
            data: [2743,1365,703,465,414,687,1684,2373,3003,3764,4455,4467,4156,4735,4582,4815,4910,4419,4016,4310,5587,7045,7529,6411]
        },
		  {
            name: '浏览',
            type: 'line',
			label: {
                normal: {
                    show: true,
                    position: 'top'
                }
            },
            data: [129242,60581,32209,20181,16380,26965,62982,95847,131606,170549,206541,194714,194793,217118,210320,209319,206061,187882,169646,190506,235321,283908,294093,235096]
        }
    ]
};
        // 使用刚指定的配置项和数据显示图表。
        myChart.setOption(option);
    </script>   
	
	
	<script type="text/javascript">
    // 基于准备好的dom，初始化echarts实例
    var myChart = echarts.init(document.getElementById('2'));
    var option = {
    title: {
        text: '不同时间段，不同性别的比例',
        subtext: '',
        left: 'center'
    },
    tooltip: {
        trigger: 'item',
        formatter: '{a} <br/>{b} : {c} ({d}%)'
    },
    legend: {
        left: 'center',
        top: 'bottom',
        data: ['男', '女']
    },
	color: ['#fdcd68','#f9a5c7','#91c7ae','#d79665','#2d84aa','#dc6d6d','#979cc9'],
    toolbox: {
        show: true,
        feature: {
            mark: {show: true},
            dataView: {show: true, readOnly: false},
            magicType: {
                show: true,
                type: ['pie', 'funnel']
            },
            restore: {show: true},
            saveAsImage: {show: true}
        }
    },
    series: [
        {
            name: '数据集总性别比例',
            type: 'pie',
            radius: [50, 150],
            center: ['25%', '50%'],
            roseType: 'radius',
            label: {
                show: false
            },
            emphasis: {
                label: {
                    show: true
                }
            },
            data: [
                {value: 126868, name: '男'},
                {value: 269064, name: '女'},
            ]
        },
		{
            name: '13：00不同性别对广告进行操作比例',
            type: 'pie',
            radius: [50, 150],
            center: ['50%', '50%'],
            roseType: 'radius',
            label: {
                show: false
            },
            emphasis: {
                label: {
                    show: true
                }
            },
            data: [
				{value: 51848, name: '男'},
                {value: 176151, name: '女'},
            ]
        },
		
		{
            name: '22：00不同性别对广告进行操作比例',
            type: 'pie',
            radius: [50, 150],
            center: ['75%', '50%'],
            roseType: 'radius',
            label: {
                show: false
            },
            emphasis: {
                label: {
                    show: true
                }
            },
            data: [
				{value: 72349, name: '男'},
                {value: 236601, name: '女'},	

            ]
        }
        
    ]
};

    // 使用刚指定的配置项和数据显示图表。
    myChart.setOption(option);
    </script>    
	
	
    <script type="text/javascript">
    // 基于准备好的dom，初始化echarts实例
    var myChart = echarts.init(document.getElementById('3'));
    var option = {
    title: {
        text: '不同时间段，不同年龄段的比例',
        subtext: '',
        left: 'center'
    },
    tooltip: {
        trigger: 'item',
        formatter: '{a} <br/>{b} : {c} ({d}%)'
    },
    legend: {
        left: 'center',
        top: 'bottom',
        data: ['年龄段0', '年龄段1','年龄段2','年龄段3','年龄段4','年龄段5','年龄段6',]
    },
	color: ['#fdcd68','#f9a5c7','#91c7ae','#d79665','#2d84aa','#dc6d6d','#979cc9'],
    toolbox: {
        show: true,
        feature: {
            mark: {show: true},
            dataView: {show: true, readOnly: false},
            magicType: {
                show: true,
                type: ['pie', 'funnel']
            },
            restore: {show: true},
            saveAsImage: {show: true}
        }
    },
    series: [
        {
            name: '数据集总年龄段比例',
            type: 'pie',
            radius: [50, 150],
            center: ['25%', '50%'],
            roseType: 'radius',
            label: {
                show: false
            },
            emphasis: {
                label: {
                    show: true
                }
            },
            data: [
                {value: 140, name: '年龄段0'},
                {value: 16734, name: '年龄段1'},
				{value: 83409, name: '年龄段2'},
				{value: 120071, name: '年龄段3'},
				{value: 94831, name: '年龄段4'},
				{value: 73721, name: '年龄段5'},
				{value: 7026, name: '年龄段6'},

            ]
        },
		{
            name: '13：00不同年龄段对广告进行操作比例',
            type: 'pie',
            radius: [50, 150],
            center: ['50%', '50%'],
            roseType: 'radius',
            label: {
                show: false
            },
            emphasis: {
                label: {
                    show: true
                }
            },
            data: [
                {value: 78, name: '年龄段0'},
                {value: 10173, name: '年龄段1'},
				{value: 49403, name: '年龄段2'},
				{value: 71208, name: '年龄段3'},
				{value: 53994, name: '年龄段4'},
				{value: 39361, name: '年龄段5'},
				{value: 3782, name: '年龄段6'},
            ]
        },
		
		{
            name: '22：00不同年龄段用户对广告进行操作比例',
            type: 'pie',
            radius: [50, 150],
            center: ['75%', '50%'],
            roseType: 'radius',
            label: {
                show: false
            },
            emphasis: {
                label: {
                    show: true
                }
            },
            data: [
                {value: 108, name: '年龄段0'},
                {value: 12767, name: '年龄段1'},
				{value: 64558, name: '年龄段2'},
				{value: 94673, name: '年龄段3'},
				{value: 75599, name: '年龄段4'},
				{value: 56403, name: '年龄段5'},
				{value: 4842, name: '年龄段6'},

            ]
        }
        
    ]
};

    // 使用刚指定的配置项和数据显示图表。
    myChart.setOption(option);
    </script>    
	
	
	
   
</body>
</html>
