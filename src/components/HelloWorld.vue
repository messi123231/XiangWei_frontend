<template>
  <div class="backMenu">
    <div class="listCharts">
      <Row class="listTop">
        <Col span="8">
          <div class="leftTop">
            <span class='title'><span>星级评分统计</span></span>
            <funnel ref="chart1" id="button_1"></funnel>
          </div>
        </Col>
        <Col span="12">
          <div class="rightTop">
            <span class='title'><span>评论时序分析</span></span>
            <lines ref="chart2"></lines>
          </div>
        </Col>
      </Row>
      <Row class="listBottom">
        <Col span='8'>
          <div class="rightBottom">
            <span class="title"><span>商铺价格统计</span></span>
            <ring ref="chart3" id="button_3" :data="data5"></ring>
          </div>
        </Col>

        <Col span='12'>
          <div class="leftBottom">
            <span class="title"><span>热点商铺分析</span></span>
            <colors-bar ref="chart4" id="button_2" :data="colorsData"></colors-bar>
          </div>
        </Col>

      </Row>
    </div>
  </div>

</template>

<script>
const colorsBar = ()=> import('./style/colorsBar.vue');
const funnel = ()=> import('./style/funnel.vue');
const lines = ()=> import('./style/lines.vue');
const ring = ()=> import('./style/ring.vue');
export default {
  name: 'chat',
  components: {
    colorsBar,
    funnel,
    lines,
    ring
  },
  data() {
    return {
      data5: {
        title: '环形图数据1',
        data: [
          {
            value: 335,
            name: '模拟1',
            itemStyle: {
              color: '#252448'
            }
          },
          {
            value: 310,
            name: '模拟2',
            itemStyle: {
              color: '#2ca8fe'
            }
          },
          {
            value: 234,
            name: '模拟3',
            itemStyle: {
              color: '#feed2c'
            }
          },
          {
            value: 135,
            name: '其他',
            itemStyle: {
              color: '#2871ea'
            }
          },
          {
            value: 200,
            name: '模拟4',
            itemStyle: {
              color: '#fe672c'
            }
          }
        ]
      },

      colorsData: [
        {
          itemStyle: {
            color: "#2c7bfe",

          },
          name: '漂流瓶',
          value: 255
        },
        {
          itemStyle: {
            color: "#c2232a",

          },
          name: '附近的人',
          value: 212
        },
        {
          itemStyle: {
            color: "#feed2c",

          },
          name: '雷达',
          value: 155
        },
        {
          itemStyle: {
            color: "#a262f2",

          },
          name: '摇一摇',
          value: 55
        },
        {
          itemStyle: {
            color: "#62d5f2",
          },
          name: '搜索',
          value: 80
        },
        {
          itemStyle: {
            color: "#fe672c",
          },
          name: '群聊',
          value: 160
        },
        {
          itemStyle: {
            color: "#69f262",
          },
          name: '扫一扫',
          value: 666
        },
        {
          itemStyle: {
            color: "#2ca8fe",
          },
          name: '其他',
          value: 20
        },
      ],
    }
  },

mounted() {
    this.$ref['chart2'].setChart()
    this.$ref['chart1'].setChart()
    this.$ref['chart3'].setChart()
}

}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="less">
.backMenu {
  height: 100%;
  width: 100%;
  .listCharts {
    height: 100%;
    width: 100%;
    padding-left: 220px;
    padding-top: 20px;
    padding-right: 10px;
    background: #030350;
    overflow: hidden;
    .title {
      position: absolute;
      display: inline-block;
      color: #6EDDF1;
      background: #14418E;
      left: 50%;
      transform: translate(-50%, -50%);
      span {
        display: inline-block;
        padding: 0.25rem 0.75rem;
        font-size: 1.2em;
        //border-radius: 5px;
        background: radial-gradient(3rem 1rem ellipse, rgba(7, 9, 34, .8) 60%, rgb(21, 67, 145));
      }
    }

    .listTop {
      height: 50%;
      width: 100%;
      padding-right: 0;

      .ivu-col {
        height: 100%;

        .leftTop {
          width: 100%;
          height: 100%;
          border: 1px solid #0D2451;
          position: relative;
        }

        .rightTop {
          width: 100%;
          height: 100%;
          border: 1px solid #0D2451;
          position: relative;
        }
      }
    }

    .listBottom {
      height: 50%;

      .leftBottom {
        width: 100%;
        height: 100%;
        border: 1px solid #0D2451;
        position: relative;
      }
      .rightBottom {
        width: 100%;
        height: 100%;
        border: 1px solid #0D2451;
        position: relative;
      }

      .ivu-col-span-9 {
        width: 33.5%;
        margin-right: 0.6667%;
      }

      .ivu-col-span-4 {
        width: 17.66667%;
        margin-right: 0.6667%;
      }

      .ivu-col {
        height: 100%;

        .content {
          margin-top: 1.5rem;
          height: calc(~"100% - 1.5rem");
          border: 1px solid #0D2451;
          position: relative;

          .title1 {
            position: absolute;
            display: inline-block;
            color: #6EDDF1;
            background: #14418E;
            left: 50%;
            transform: translate(-50%, -50%);

            span {
              display: inline-block;
              padding: 0.25rem 0.75rem;
              font-size: 1.2em;
              background: radial-gradient(2.5rem 1.025rem ellipse, rgba(7, 9, 34, .8) 50%, rgb(21, 67, 145));
            }

          }
        }
      }
    }
  }
}



</style>
