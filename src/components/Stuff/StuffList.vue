<template>
  <div>
    <el-breadcrumb separator="/">
      <el-breadcrumb-item :to="{ path: '/' }">首页</el-breadcrumb-item> 
      <el-breadcrumb-item>部门列表</el-breadcrumb-item>
    </el-breadcrumb>
    <el-card v-for="stuff in dataList" :key='stuff.stuffID' class="box-card">
      <div slot="header" class="clearfix">
      <span>{{stuff.name}}</span>
      <el-button style="float: right; padding: 3px 0" type="text" @click="goDetail(stuff.stuffID)">详细信息</el-button>
      </div>
      <img class="stuff-pic" src="@/assets/logo.png" alt="">
      <div class="text item">简介：{{stuff.information}}</div>
      <div class="text item">部门人数：{{stuff.memberAmount}}</div>
    </el-card>
  </div>
</template>
<script>
export default {
  name: 'StuffList',
  data () {
    return {
      msg: '2233',
      dataList: [
        {
          stuffID: 0,
          name: '',
          information: '',
          memberAmount: 0
        }
      ]
    }
  },
  computed: {
  },
  methods: {
    goDetail: function (id) {
      this.$router.push({name: 'StuffDetail', params: {id: id}})
    }
  },
  mounted () {
    this.dataList = [
      {
        stuffID: 1,
        name: '人事部',
        information: '人事部是一个企业或者团体的人力资源和企业公共事务的管理部门 。现在为强化人的重要性，分离出人力资源部门。',
        memberAmount: 100
      },
      {
        stuffID: 2,
        name: 'stuff1',
        information: 'info1',
        memberAmount: 100
      }
    ]
  }
}
</script>
<style>
  .text {
    font-size: 14px;
  }

  .item {
    margin-bottom: 18px;
  }

  .clearfix:before,
  .clearfix:after {
    display: table;
    content: "";
  }
  .clearfix:after {
    clear: both
  }
</style>
<style scoped>
.el-card {
  margin-bottom: 10px;
}
.stuff-pic {
  width: 150px;
  height: 120px;
  float: left;
  margin: 0 2%;
}
</style>

