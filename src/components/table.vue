<template>
  <div id="detail">
    <div id="title">
      <p style="width: 10%"><i class="el-icon-arrow-left"></i></p>
      <p style="width: 80%">财务明细</p>
      <p style="width: 10%"></p>
    </div>
    <div id="tabs">
      <el-tabs v-model="activeName" @tab-click="handleClick">
        <el-tab-pane label="原始资产" name="first">
          <el-table
            :data="tableData"
            height="350"
            style="width: 100%">
            <el-table-column
              prop="time"
              label="记录时间">
            </el-table-column>
            <el-table-column
              prop="change"
              label="变动">
            </el-table-column>
            <el-table-column
              prop="balance"
              label="余额">
            </el-table-column>
            <el-table-column
              prop="description"
              label="说明">
            </el-table-column>
          </el-table>
          <!--分页-->
          <div class="block">
            <el-pagination
              layout="prev, pager, next"
              @current-change="getData()"
              :current-page.sync="currentPage"
              :page-size="5"
              :total="6">
            </el-pagination>
          </div>
        </el-tab-pane>
        <el-tab-pane label="矿池钱包" name="second">
          <!--分页-->
          <div class="block">
            <el-pagination
              layout="prev, pager, next"
              @current-change="getData()"
              :current-page.sync="currentPage"
              :page-size="5"
              :total="0">
            </el-pagination>
          </div>
        </el-tab-pane>
        <el-tab-pane label="矿池资产" name="third">
          <!--分页-->
          <div class="block">
            <el-pagination
              layout="prev, pager, next"
              @current-change="getData()"
              :current-page.sync="currentPage"
              :page-size="5"
              :total="0">
            </el-pagination>
          </div>
        </el-tab-pane>
      </el-tabs>
    </div>
  </div>
</template>
<script>
  export default {
    data() {
      return {
        activeName: 'first',
        currentPage: 1,
        clientHeight:0,
        tableData: []
      };
    },
    methods: {
      handleClick(tab, event) {
        console.log(tab, event);
      },
      getData(page = this.currentPage) {
        this.tableData = page == 2 ? [{
          time: '2019-1-2',
          change: '变动7878',
          balance: '余额7878',
          description:'说明999'
        }]:[{
           time: '2016-05-02',
           change: '变动111',
           balance: '余额111',
           description:'说明111'
         }, {
           time: '2017-08-02',
           change: '变动222',
           balance: '余额222',
           description:'说明222'
         }, {
           time: '2017-09-02',
           change: '变动333',
           balance: '余额333',
           description:'说明333'
         }, {
           time: '2017-09-02',
           change: '变动333',
           balance: '余额333',
           description:'说明333',
         },
           {
             time: '2017-09-02',
             change: '变动333',
             balance: '余额333',
             description:'说明333'
           },
          {
            time: '2017-09-02',
            change: '变动333',
            balance: '余额333',
            description:'说明333'
          }, {
            time: '2017-09-02',
            change: '变动333',
            balance: '余额333',
            description:'说明333',
          },
          {
            time: '2017-09-02',
            change: '变动333',
            balance: '余额333',
            description:'说明333'
          }
         ]

      },
    },
    created(){
        this.tableData = [{
          time: '2016-05-02',
          change: '变动111',
          balance: '余额111',
          description:'说明111'
        }, {
          time: '2017-08-02',
          change: '变动222',
          balance: '余额222',
          description:'说明222'
        }, {
          time: '2017-09-02',
          change: '变动333',
          balance: '余额333',
          description:'说明333'
        }, {
          time: '2017-09-02',
          change: '变动333',
          balance: '余额333',
          description:'说明333',
        },
          {
            time: '2017-09-02',
            change: '变动333',
            balance: '余额333',
            description:'说明333'
          },
          {
            time: '2017-09-02',
            change: '变动333',
            balance: '余额333',
            description:'说明333'
          }, {
            time: '2017-09-02',
            change: '变动333',
            balance: '余额333',
            description:'说明333',
          },
          {
            time: '2017-09-02',
            change: '变动333',
            balance: '余额333',
            description:'说明333'
          }
        ]
    }
  };
</script>

<style lang="scss"  scoped>
  #detail{
    background-color: #3E48AA;
  }
  #title{
    height: 75px;
    color: #ffffff;
    line-height: 75px;
    font-size: 16px;
    font-weight: bold;
  }
  #title p{
    float: left;
    margin: 0;
    color: #ffffff;
  }
  #tabs{
    font-size: 14px;
    background-color: #fff;
    border-top-right-radius: 10px;
    border-top-left-radius: 10px
  }


</style>
