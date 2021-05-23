<template>
  <div>
    <el-form ref="form" :model="form" :inline="true">
      <el-form-item label="关键词">
        <el-input v-model="form.name"></el-input>
      </el-form-item>
      <el-form-item label="跳转方式">
        <el-select v-model="form.region" :clearable="true">
          <el-option
            v-for="item in typeList"
            :key="item.value"
            :label="item.name"
            :value="item.value"
          ></el-option>
        </el-select>
      </el-form-item>
      <el-form-item>
        <el-button type="primary">查询</el-button>
        <el-button>新增</el-button>
      </el-form-item>
    </el-form>
    <el-table :data="tableData" border style="width: 100%">
      <el-table-column type="index" label="序号" width="80"></el-table-column>
      <el-table-column prop="date" label="名称"></el-table-column>
      <el-table-column prop="name" label="描述"> </el-table-column>
      <el-table-column prop="address" label="图标"> </el-table-column>
      <el-table-column prop="address" label="跳转方式"></el-table-column>
      <el-table-column prop="address" label="创建时间"></el-table-column>
      <el-table-column prop="address" label="操作">
        <template>
          <el-button type="text" size="small">删除</el-button>
          <el-button type="text" size="small">修改</el-button>
          <el-button type="text" size="small">置顶</el-button>
          <el-button type="text" size="small">隐藏</el-button>
        </template>
      </el-table-column>
    </el-table>
  </div>
</template>

<script>
import CONST from './data'
export default {
  data() {
    return {
      form: {},
      tableData: [],
      typeList: CONST.HREF_TYPE_LIST
    };
  },
};
</script>

<style>
</style>
