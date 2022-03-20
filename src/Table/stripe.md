---
title: 斑马线条纹
order: 6
group:
  path: /base
  title: 基础表格
  order: 1
---
## 斑马线条纹

> 通过设置`stripe`参数 实现斑马线条纹

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
      ellipsis: true,
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
    { name: '李四爆炸啦~李四爆炸啦~李四爆炸啦~李四爆炸啦~李四爆炸啦~李四爆炸啦~李四爆炸啦~李四爆炸啦~李四爆炸啦~李四爆炸啦~李四爆炸啦~李四爆炸啦~李四爆炸啦~', sex: '男', age: '22' },
    { name: '小红', sex: '女', age: '16' },
    { name: '王五不见啦~王五不见啦~王五不见啦~王五不见啦~王五不见啦~王五不见啦~王五不见啦~王五不见啦~王五不见啦~王五不见啦~王五不见啦~', sex: '男', age: '12' },
  ]

  return <CkTable columns={columns} data={tableData} stripe />;
};
export default Base;
```

> 通过给表格设置`rowConfig={{ isHover: true }}`启用hover行高亮

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
      ellipsis: true,
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
    { name: '李四爆炸啦~李四爆炸啦~李四爆炸啦~李四爆炸啦~李四爆炸啦~李四爆炸啦~李四爆炸啦~李四爆炸啦~李四爆炸啦~李四爆炸啦~李四爆炸啦~李四爆炸啦~李四爆炸啦~', sex: '男', age: '22' },
    { name: '小红', sex: '女', age: '16' },
    { name: '王五不见啦~王五不见啦~王五不见啦~王五不见啦~王五不见啦~王五不见啦~王五不见啦~王五不见啦~王五不见啦~王五不见啦~王五不见啦~', sex: '男', age: '12' },
  ]

  return <CkTable columns={columns} data={tableData} rowConfig={{ isHover: true }} stripe />;
};
export default Base;
```