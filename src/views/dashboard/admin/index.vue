<template>
  <div class="dashboard-editor-container">
    <github-corner class="github-corner" />

    <panel-group @handleSetLineChartData="handleSetLineChartData" />
    <el-row :gutter="12">
      <el-col :span="16">
        <el-card shadow="hover">
          <div>
            <p align="center">
              <img src="https://cdn.learnku.com/uploads/images/202005/17/18206/zSuf7Ce5kM.png!large">
            </p>
            <p align="center"><code>CatchAdmin</code>是一款基于<a href="http://www.thinkphp.cn/" target="_blank">thinkphp framework</a>和
              <a href="https://pro.loacg.com/docs/getting-started">ant degisn pro vue</a>二次开发而成的后台管理系统，采用了目前趋势的前后端分离开发模式，后端仅需要提供简洁的 API 数据结构，前端负责呈现数据。目前前端采用数据驱动，大大提高了开发效率。这不仅仅是一个项目，更是后端更新技术栈的一次实践</p>
            <p align="center">
              <a href="http://doc.catchadmin.com/">文档</a> |
              <a href="http://vue.catchadmin.com">演示地址</a> |
              <a href="http://apidoc.catchadmin.com">接口文档</a> |
              <a href="https://gitee.com/jaguarjack/catchAdmin">项目源码</a> |
              <a href="https://www.kancloud.cn/akasishikelu/thinkphp6">看云分析</a> |
              <a href="#extensions">扩展</a>
            </p>
            <div align="center">
              <a href="https://gitee.com/jaguarjack/catchAdmin" target="_blank">
                <img src="https://svg.hamm.cn/gitee.svg?type=star&user=jaguarjack&project=catchAdmin" />
              </a >
              <a href="https://gitee.com/jaguarjack/catchAdmin" target="_blank">
                <img src="https://svg.hamm.cn/gitee.svg?type=fork&user=jaguarjack&project=catchAdmin" style="margin-left: 10px;"/>
              </a >
              <a>
                <img src="https://svg.hamm.cn/badge.svg?key=Base&value=ThinkPHP6" style="margin-left: 10px;"/>
              </a>
              <a>
                <img src="https://svg.hamm.cn/badge.svg?key=Data&value=MySQL5.5" style="margin-left: 10px;"/>
              </a>
              <a>
                <img src="https://svg.hamm.cn/badge.svg?key=Runtime&value=PHP7.1" style="margin-left: 10px;"/>
              </a>
              <a>
                <img src="https://svg.hamm.cn/badge.svg?key=License&value=Apache-2.0" style="margin-left: 10px;"/>
              </a>
            </div>
          </div>
        </el-card>
      </el-col>
      <el-col :span="8">
        <el-card shadow="hover">
          其实这里不该说些什么了，祝大家用的愉快吧！有 BUG 早点提奥！😄
        </el-card>
      </el-col>
    </el-row>
    <!--
    <el-row style="background:#fff;padding:16px 16px 0;margin-bottom:32px;">
      <line-chart :chart-data="lineChartData" />
    </el-row>

    <el-row :gutter="32">
      <el-col :xs="24" :sm="24" :lg="8">
        <div class="chart-wrapper">
          <raddar-chart />
        </div>
      </el-col>
      <el-col :xs="24" :sm="24" :lg="8">
        <div class="chart-wrapper">
          <pie-chart />
        </div>
      </el-col>
      <el-col :xs="24" :sm="24" :lg="8">
        <div class="chart-wrapper">
          <bar-chart />
        </div>
      </el-col>
    </el-row>

    <el-row :gutter="8">
      <el-col :xs="{span: 24}" :sm="{span: 24}" :md="{span: 24}" :lg="{span: 12}" :xl="{span: 12}" style="padding-right:8px;margin-bottom:30px;">
        <transaction-table />
      </el-col>
      <el-col :xs="{span: 24}" :sm="{span: 12}" :md="{span: 12}" :lg="{span: 6}" :xl="{span: 6}" style="margin-bottom:30px;">
        <todo-list />
      </el-col>
      <el-col :xs="{span: 24}" :sm="{span: 12}" :md="{span: 12}" :lg="{span: 6}" :xl="{span: 6}" style="margin-bottom:30px;">
        <box-card />
      </el-col>
    </el-row> -->
  </div>
</template>

<script>
import GithubCorner from '@/components/GithubCorner'
import PanelGroup from './components/PanelGroup'
import LineChart from './components/LineChart'
import RaddarChart from './components/RaddarChart'
import PieChart from './components/PieChart'
import BarChart from './components/BarChart'
import TransactionTable from './components/TransactionTable'
import TodoList from './components/TodoList'
import BoxCard from './components/BoxCard'

const lineChartData = {
  newVisitis: {
    expectedData: [100, 120, 161, 134, 105, 160, 165],
    actualData: [120, 82, 91, 154, 162, 140, 145]
  },
  messages: {
    expectedData: [200, 192, 120, 144, 160, 130, 140],
    actualData: [180, 160, 151, 106, 145, 150, 130]
  },
  purchases: {
    expectedData: [80, 100, 121, 104, 105, 90, 100],
    actualData: [120, 90, 100, 138, 142, 130, 130]
  },
  shoppings: {
    expectedData: [130, 140, 141, 142, 145, 150, 160],
    actualData: [120, 82, 91, 154, 162, 140, 130]
  }
}

export default {
  name: 'DashboardAdmin',
  components: {
    GithubCorner,
    PanelGroup,
    LineChart,
    RaddarChart,
    PieChart,
    BarChart,
    TransactionTable,
    TodoList,
    BoxCard
  },
  data() {
    return {
      lineChartData: lineChartData.newVisitis
    }
  },
  methods: {
    handleSetLineChartData(type) {
      this.lineChartData = lineChartData[type]
    }
  }
}
</script>

<style lang="scss" scoped>
.dashboard-editor-container {
  padding: 32px;
  background-color: rgb(240, 242, 245);
  position: relative;

  .github-corner {
    position: absolute;
    top: 0px;
    border: 0;
    right: 0;
  }

  .chart-wrapper {
    background: #fff;
    padding: 16px 16px 0;
    margin-bottom: 32px;
  }
}

@media (max-width:1024px) {
  .chart-wrapper {
    padding: 8px;
  }
}
</style>
