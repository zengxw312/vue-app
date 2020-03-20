<template>
  <div class="about">
   <div id="char2" style="width: 100%;height:300px;"></div>
  </div>
</template>
<script>
import echarts from 'echarts'
export default {

  data(){
    return {
    }
  },

  mounted(){   //生命周期
      this.init();
  },
  methods:{
    init(){
      //基于准备好的dom初始化ecartts实例
      var myChar=echarts.init(document.getElementById('char2'));
      var option={
        title:{
          text:'全国   新增确诊/疑似  趋势',
          x:'center',
          textStyle:{
           color:'#999'
          }
        },
        tooltip:{
          trigger:'axis'
        },
        legend:{
          data:['新增确诊','新增疑似'],
          top:'30'
        },
        grid:{
          left:'3%',
          right:'4%',
          bottom:'3%',
          containLabel:true
        },
        toolbox:{
          feature:{
            daveAsImage:{}
          }
        },
        xAxis:{
          type:'category',
          data:['2.11','2.12','2.13','2.14','2.15','2.16','2.17','2.18','2.19','2.20','2.21','2.22']
        },
        yAxis:{
          type:'value',
        },
        series:[
          {
            name:'新增确诊',
            type:'line',
            smooth:true,
            data:[2022,15153,5949,2593,3323,2343,5435,3423,2323,3423,2334,1242]
          },
             {
            name:'新增疑似',
            type:'line',
            smooth:true,
            data:[2342,10063,5934,2333,3545,2143,5435,3423,233,3423,2344,142]
          },
        ]
      };
      myChar.setOption(option);

    }

  }
  
}
</script>