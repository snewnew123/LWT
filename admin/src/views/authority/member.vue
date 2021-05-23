<template>
  <div>
    <el-form ref="form" :model="form" :inline="true">
      <el-form-item label="名称">
        <el-input v-model="form.name"></el-input>
      </el-form-item>
      <el-form-item label="手机号">
        <el-input v-model="form.name"></el-input>
      </el-form-item>
      <el-form-item label="角色权限">
        <el-select v-model="form.region" :clearable="true">
          <el-option v-for="item in ROLE_LIST" :key="item.value" :label="item.name" :value="item.value"></el-option>
        </el-select>
      </el-form-item>
      <el-form-item>
        <el-button type="primary">查询</el-button>
        <el-button @click="dialogFormVisible = true">新增</el-button>
      </el-form-item>
    </el-form>
    <el-table :data="tableData" border style="width: 100%">
      <el-table-column type="index" label="序号" width="80"></el-table-column>
      <el-table-column prop="date" label="名称"></el-table-column>
      <el-table-column prop="name" label="手机号"> </el-table-column>
      <el-table-column prop="address" label="角色权限"> </el-table-column>
      <el-table-column prop="address" label="创建时间吗"> </el-table-column>
      <el-table-column prop="address" label="操作">
        <template>
          <el-button type="text" size="small">修改</el-button>
          <el-button type="text" size="small">删除</el-button>
        </template>
      </el-table-column>
    </el-table>

    <el-dialog title="收货地址" :visible.sync="dialogFormVisible" :close-on-click-modal="false" width="500px">
      <el-form :model="EditForm" label-width="80px">
        <el-form-item label="名称">
          <el-input v-model="form.name" autocomplete="off"></el-input>
        </el-form-item>
        <el-form-item label="手机号">
          <el-input v-model="form.name" autocomplete="off"></el-input>
        </el-form-item>
        <el-form-item label="角色权限">
          <el-select v-model="EditForm.role">
            <el-option v-for="item in ROLE_LIST" :key="item.value" :label="item.name" :value="item.value"></el-option>
          </el-select>
        </el-form-item>
      </el-form>
      <div slot="footer" class="dialog-footer">
        <el-button @click="dialogFormVisible = false">取 消</el-button>
        <el-button type="primary" @click="dialogFormVisible = false"
          >确 定</el-button
        >
      </div>
    </el-dialog>
  </div>
</template>

<script>
import CONST from './data'
export default {
  name: "member",
  data() {
    return {
      form: {},
      tableData: [{}],
      EditForm: {
        role: 1
      },
      dialogFormVisible: false,
      ROLE_LIST: CONST.ROLE_LIST
    };
  },
};
</script>

<style lang="scss" scoped>
</style>
