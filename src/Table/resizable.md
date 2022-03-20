---
title: 列宽拖动
order: 11
group:
  path: /base
  title: 基础表格
  order: 1
---

## 列宽拖动
> `resizable`开启列宽拖动    

```jsx
import React from 'react';
import CkTable from 'ck-table';

const Base = () => {
  const [border, setBorder] = React.useState('full');
  const columns = [
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
      fixed: 'left',
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

  return <CkTable columns={columns} data={tableData} resizable border={border} height={300} />;
};
export default Base;
```