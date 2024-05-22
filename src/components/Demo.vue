<template>
  <el-table
    :data="tableData"
    style="width: 100%"
    :border="true"
    @selection-change="handleSelectionChange"
  >
    <el-table-column type="selection" width="55" />
    <el-table-column prop="date" label="服务部门" />
    <el-table-column prop="date" label="消息内容" />
    <el-table-column prop="date" label="消息明细" width="1000">
      <template #default="scope">
        <el-table :data="tableData2" style="width: 100%">
          <el-table-column type="selection" width="55" />
          <el-table-column prop="date" label="序号" width="180" />
          <el-table-column prop="name" label="项目名称" width="180" />
          <el-table-column prop="name" label="单位" />
          <el-table-column prop="name" label="数量" />
          <el-table-column prop="name" label="应收金额" />
          <el-table-column prop="name" label="备注" />
          <el-table-column prop="name" label="发送状态" />
        </el-table>
      </template>
    </el-table-column>
  </el-table>
</template>

<script lang="ts" setup>
// https://element-plus.org/zh-CN/component/table.html#%E5%A4%9A%E9%80%89
import { ref } from "vue";

interface User {
  date: string;
  name: string;
  address: string;
}

const multipleSelection = ref<User[]>([]);

const handleSelectionChange = (val: User[]) => {
  multipleSelection.value = val;
};

const tableData = [
  {
    date: "2016-05-03",
    name: "Tom",
    state: "California",
    city: "Los Angeles",
    address: "No. 189, Grove St, Los Angeles",
    zip: "CA 90036",
  },
  {
    date: "2016-05-02",
    name: "Tom",
    state: "California",
    city: "Los Angeles",
    address: "No. 189, Grove St, Los Angeles",
    zip: "CA 90036",
  },
  {
    date: "2016-05-04",
    name: "Tom",
    state: "California",
    city: "Los Angeles",
    address: "No. 189, Grove St, Los Angeles",
    zip: "CA 90036",
  },
  {
    date: "2016-05-01",
    name: "Tom",
    state: "California",
    city: "Los Angeles",
    address: "No. 189, Grove St, Los Angeles",
    zip: "CA 90036",
  },
  {
    date: "2016-05-08",
    name: "Tom",
    state: "California",
    city: "Los Angeles",
    address: "No. 189, Grove St, Los Angeles",
    zip: "CA 90036",
  },
];

const tableData2 = [
  {
    date: "2016-05-03",
    name: "Tom",
    state: "California",
    city: "Los Angeles",
    address: "No. 189, Grove St, Los Angeles",
    zip: "CA 90036",
  },
  {
    date: "2016-05-02",
    name: "Tom",
    state: "California",
    city: "Los Angeles",
    address: "No. 189, Grove St, Los Angeles",
    zip: "CA 90036",
  },
];
</script>
