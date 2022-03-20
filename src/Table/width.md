---
title: 列宽
order: 4
group:
  path: /base
  title: 基础表格
  order: 1
---
## 列宽

> 列宽，通过设置width参数，默认: 250, 如果宽度小于表格的宽度，则会等比分配
```jsx
import React from 'react';
import CkTable from 'ck-table';

const Base = () => {
  const columns = [
    {
      Header: '#',
      type: 'seq',
      accessor: 'seq',
      width: 100,
    },
    {
      Header: 'Name',
      accessor: 'name',
      width: 100,
    },
    {
      Header: 'Sex',
      accessor: 'sex',
      width: 100,
    },
    {
      Header: 'Age',
      accessor: 'age',
      width: 100,
    },
  ]

  const tableData = [
    { name: '张三', sex: '男', age: '18' },
    { name: '李四', sex: '男', age: '22' },
    { name: '小红', sex: '女', age: '16' },
    { name: '王五', sex: '男', age: '12' },
  ]

  return <CkTable columns={columns} data={tableData} />;
};
export default Base;
```

> 设置固定和最大宽度，用于固定宽度，不会等比放大
```jsx
import React from 'react';
import CkTable from 'ck-table';

const Base = () => {
  const columns = [
    {
      Header: '#',
      type: 'seq',
      accessor: 'seq',
      width: 100,
    },
    {
      Header: 'Name',
      accessor: 'name',
      width: 100,
      maxWidth: 120,
    },
    {
      Header: 'Sex',
      accessor: 'sex',
      width: 100,
      width: 100,
    },
    {
      Header: 'Age',
      accessor: 'age',
      width: 100,
    },
  ]

  const tableData = [
    { name: '张三', sex: '男', age: '18' },
    { name: '李四', sex: '男', age: '22' },
    { name: '小红', sex: '女', age: '16' },
    { name: '王五', sex: '男', age: '12' },
  ]

  return <CkTable columns={columns} data={tableData} />;
};
export default Base;
```

> 设置最小宽度，默认最小宽度: 60, 最小和最大宽度用于拖拽列宽  
> 默认的浏览器宽度大小改变缩放列宽度不会小于固定宽度: width
```jsx
import React from 'react';
import CkTable from 'ck-table';

const Base = () => {
  const columns = [
    {
      Header: '#',
      type: 'seq',
      accessor: 'seq',
      width: 100,
    },
    {
      Header: 'Name',
      accessor: 'name',
      width: 200,
      minWidth: 100,
      maxWidth: 300,
    },
    {
      Header: 'Sex',
      accessor: 'sex',
      width: 100,
    },
    {
      Header: 'Age',
      accessor: 'age',
      width: 100,
    },
  ]

  const tableData = [
    { name: '张三', sex: '男', age: '18' },
    { name: '李四', sex: '男', age: '22' },
    { name: '小红', sex: '女', age: '16' },
    { name: '王五', sex: '男', age: '12' },
  ]

  return <CkTable columns={columns} data={tableData} resizable />;
};
export default Base;
```