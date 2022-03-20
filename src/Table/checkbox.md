---
title: 复选框
order: 15
group:
  path: /base
  title: 基础表格
  order: 1
---
## 复选框

> 列设置`type: 'checkbox'`启用复选框   
```jsx
import React from 'react';
import CkTable from 'ck-table';
import 'antd/dist/antd.css';

const Base = () => {
  const columns = [
    {
      Header: 'checkbox',
      type: 'checkbox',
      accessor: 'checkbox',
      width: 80,
      maxWidth: 80,
      fixed: 'left',
    },
    {
      Header: '#',
      type: 'seq',
      accessor: 'seq',
      width: 200,
    },
    {
      Header: 'Name',
      accessor: 'name',
      width: 200,
      ellipsis: true,
    },
    {
      Header: 'Sex',
      accessor: 'sex',
      width: 200,
    },
    {
      Header: 'Age',
      accessor: 'age',
      width: 200,
    },
    {
      Header: 'Address',
      accessor: 'address',
      width: 800,
      ellipsis: true,
    },
  ]

  const tableData = [
    { name: '张三', sex: '男', age: '18', address: '浙江省杭州市滨江区犄角旮旯里' },
    { name: '李四爆炸啦~', sex: '男', age: '22', address: '浙江省杭州市滨江区犄角旮旯里' },
    { name: '小红', sex: '女', age: '16', address: '浙江省杭州市滨江区犄角旮旯里' },
    { name: '王五不见啦~', sex: '男', age: '12', address: '浙江省杭州市滨江区犄角旮旯里' },
    { name: '王五不见啦~', sex: '男', age: '12', address: '浙江省杭州市滨江区犄角旮旯里' },
    { name: '王五不见啦~', sex: '男', age: '12', address: '浙江省杭州市滨江区犄角旮旯里' },
    { name: '王五不见啦~', sex: '男', age: '12', address: '浙江省杭州市滨江区犄角旮旯里' },
    { name: '王五不见啦~', sex: '男', age: '12', address: '浙江省杭州市滨江区犄角旮旯里' },
    { name: '王五不见啦~', sex: '男', age: '12', address: '浙江省杭州市滨江区犄角旮旯里' },
    { name: '王五不见啦~', sex: '男', age: '12', address: '浙江省杭州市滨江区犄角旮旯里' },
    { name: '王五不见啦~', sex: '男', age: '12', address: '浙江省杭州市滨江区犄角旮旯里' },
    { name: '王五不见啦~', sex: '男', age: '12', address: '浙江省杭州市滨江区犄角旮旯里' },
  ]

  return <CkTable columns={columns} data={tableData} stripe height={300} />;
};
export default Base;
```

> 通过`checkboxConfig: {Control: (...) => {...}}`配置复选框组件，以下示例使用了Antd的`Checkbox`组件    
```jsx
import React from 'react';
import CkTable from 'ck-table';
import { Checkbox } from 'antd';

const Base = () => {
  const columns = [
    {
      Header: 'checkbox',
      type: 'checkbox',
      accessor: 'checkbox',
      width: 80,
      maxWidth: 80,
      fixed: 'left',
    },
    {
      Header: '#',
      type: 'seq',
      accessor: 'seq',
      width: 200,
    },
    {
      Header: 'Name',
      accessor: 'name',
      width: 200,
      ellipsis: true,
    },
    {
      Header: 'Sex',
      accessor: 'sex',
      width: 200,
    },
    {
      Header: 'Age',
      accessor: 'age',
      width: 200,
    },
    {
      Header: 'Address',
      accessor: 'address',
      width: 800,
      ellipsis: true,
    },
  ]

  const tableData = [
    { name: '张三', sex: '男', age: '18', address: '浙江省杭州市滨江区犄角旮旯里' },
    { name: '李四爆炸啦~', sex: '男', age: '22', address: '浙江省杭州市滨江区犄角旮旯里' },
    { name: '小红', sex: '女', age: '16', address: '浙江省杭州市滨江区犄角旮旯里' },
    { name: '王五不见啦~', sex: '男', age: '12', address: '浙江省杭州市滨江区犄角旮旯里' },
    { name: '王五不见啦~', sex: '男', age: '12', address: '浙江省杭州市滨江区犄角旮旯里' },
    { name: '王五不见啦~', sex: '男', age: '12', address: '浙江省杭州市滨江区犄角旮旯里' },
    { name: '王五不见啦~', sex: '男', age: '12', address: '浙江省杭州市滨江区犄角旮旯里' },
    { name: '王五不见啦~', sex: '男', age: '12', address: '浙江省杭州市滨江区犄角旮旯里' },
    { name: '王五不见啦~', sex: '男', age: '12', address: '浙江省杭州市滨江区犄角旮旯里' },
    { name: '王五不见啦~', sex: '男', age: '12', address: '浙江省杭州市滨江区犄角旮旯里' },
    { name: '王五不见啦~', sex: '男', age: '12', address: '浙江省杭州市滨江区犄角旮旯里' },
    { name: '王五不见啦~', sex: '男', age: '12', address: '浙江省杭州市滨江区犄角旮旯里' },
  ]

  const checkboxConfig = {
    Control: (resetProps) => <Checkbox {...resetProps} />,
  }

  return <CkTable columns={columns} checkboxConfig={checkboxConfig} data={tableData} height={300} />;
};
export default Base;
```