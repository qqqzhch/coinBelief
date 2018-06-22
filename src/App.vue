<template>
  <div id="app">
    <highcharts :options="options"></highcharts>
    <HelloWorld  v-on:myevent="doSomething"/>

  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld'

export default {
  name: 'App',
  methods: {
    doSomething: function (item){
      console.log('========')
      console.log(item)
      var result= {team:0,community:0,whitepaper:0,finance:0,partners:0,dev:0}
      item.forEach(function(item){
      result.team+=item.team;
      result.community+=item.community;
      result.whitepaper+=item.whitepaper;
      result.finance+=item.finance;
      result.partners+=item.partners;
      result.dev+=item.dev;

      })
      //这个是计算结果的和
      //就得有个地方记录选择了哪些数据
      this.options.series[0].data=[
      result.team,
      result.community,
      result.whitepaper,
      result.finance,
      result.partners,
      result.dev
      ]


     }

  },
  data() {
  var options = {
  chart: {
    polar: true,
    type: 'area'
},
title: {
    text: '币的信仰组成',

},
credits:{
   enabled:false
},
pane: {
    size: '80%'
},
xAxis: {
    categories: ['创始团队', '社区营销','白皮书 ','财务透明','应用','研发进度'],
    tickmarkPlacement: 'on',
    lineWidth: 0
},
yAxis: {
    gridLineInterpolation: 'polygon',
    lineWidth: 0,
    min: 0
},
tooltip: {
    shared: true,
    pointFormat: '<span style="color:{series.color}">{series.name}: <b>${point.y:,.0f}</b><br/>'
},
legend: {
enabled:false

},
series: [{
    name: '-',
    data: [10, 10, 10, 10, 10, 10],
    pointPlacement: 'on'
}]
  };
    return  {test1:'名称',options:options}

  },
  components: {
   HelloWorld
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.bg {
  background: url(http://www.lambda.im/img/universe-bg22f4407ea20f2049aaf44407e8024ed0.jpg) no-repeat;
  background-size: cover;
  height: 100%;
  width: 100%;
  position: fixed;
  top: 0;
  left: 0;
  z-index: -3;
}
</style>
