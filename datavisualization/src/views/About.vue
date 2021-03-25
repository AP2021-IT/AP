<template>
<div>
  <div class="p-grid">
    <Chart type="polarArea" :data="chartData" />

	<div class="p-col-12 p-md-6 p-lg-3"><Chart type="bar" :data="basicData" /></div>
	<div class="p-col-12 p-md-6 p-lg-3"><Chart type="horizontalBar" :data="basicData" /></div>
	<div class="p-col-12 p-md-6 p-lg-3"><Chart type="bar" :data="multiAxisData" :options="multiAxisOptions"/></div>
	<div class="p-col-12 p-md-6 p-lg-3"><Chart type="bar" :data="stackedData" :options="stackedOptions"/></div>
</div>
</div>
</template>
<script>
// import { defineComponent } from '@vue/composition-api'



export default {
	data() {
		return {
			basicData: {
				labels: ['January', 'February', 'March', 'April', 'May', 'June', 'July'],
				datasets: [
					{
						label: 'My First dataset',
						backgroundColor: '#42A5F5',
						data: [65, 59, 80, 81, 56, 55, 40]
					},
					{
						label: 'My Second dataset',
						backgroundColor: '#FFA726',
						data: [28, 48, 40, 19, 86, 27, 90]
					}
				]
			},
			multiAxisData: {
				labels: ['January', 'February', 'March', 'April', 'May', 'June', 'July'],
				datasets: [
					{
						label: 'Dataset 1',
						backgroundColor: [
                            '#EC407A',
                            '#AB47BC',
                            '#42A5F5',
                            '#7E57C2',
                            '#66BB6A',
                            '#FFCA28',
                            '#26A69A'
						],
						yAxisID: 'y-axis-1',
						data: [65, 59, 80, 81, 56, 55, 10]
					},
					{
						label: 'Dataset 2',
						backgroundColor: '#78909C',
						yAxisID: 'y-axis-2',
						data: [28, 48, 40, 19, 86, 27, 90]
					}
				]
			},
			multiAxisOptions: {
				responsive: true,
				tooltips: {
					mode: 'index',
					intersect: true
				},
				scales: {
					yAxes: [
						{
							type: 'linear',
							display: true,
							position: 'left',
							id: 'y-axis-1',
							ticks: {
								min: 0,
								max: 100
							}
						},
						{
							type: 'linear',
							display: true,
							position: 'right',
							id: 'y-axis-2',
							gridLines: {
								drawOnChartArea: false
							},
							ticks: {
								min: 0,
								max: 100
							}
						}
					]
				}
			},
			stackedData: {
				labels: ['January', 'February', 'March', 'April', 'May', 'June', 'July'],
				datasets: [
					{
						type: 'bar',
						label: 'Dataset 1',
						backgroundColor: '#42A5F5',
						data: [
							50,
							25,
							12,
							48,
							90,
							76,
							42
						]
					},
					{
						type: 'bar',
						label: 'Dataset 2',
						backgroundColor: '#66BB6A',
						data: [
							21,
							84,
							24,
							75,
							37,
							65,
							34
						]
					},
					{
						type: 'bar',
						label: 'Dataset 3',
						backgroundColor: '#FFA726',
						data: [
							41,
							52,
							24,
							74,
							23,
							21,
							32
						]
					}
				]
			},
			stackedOptions: {
				tooltips: {
					mode: 'index',
					intersect: false
				},
				responsive: true,
				scales: {
					xAxes: [{
						stacked: true,
					}],
					yAxes: [{
						stacked: true
					}]
				}
			},
      chartData: {
				datasets: [{
					data: [
						11,
						16,
						7,
						3,
						14
					],
					backgroundColor: [
						"#42A5F5",
                        "#66BB6A",
                        "#FFA726",
                        "#26C6DA",
                        "#7E57C2"
					],
					label: 'My dataset'
				}],
				labels: [
					"Red",
					"Green",
					"Yellow",
					"Grey",
					"Blue"
				]
			}
		}
		
	}
}

</script>