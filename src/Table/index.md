---
title: 基础
order: 1
group:
  path: /base
  title: 基础表格
  order: 1
---
## 基础表格

与传统表格使用方式一样，使用非常简单！
```tsx
import React from 'react';
import CkTable from 'ck-table';
import { Table } from 'ck-table-dosc';

const Base = () => {

  const columns = [
    {
      title: 'Name',
      accessor: 'name',
      width: 100,
    },
    {
      title: 'Sex',
      accessor: 'sex',
      width: 100,
    },
    {
      title: 'Age',
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

  return (
    <>
      <Table title="直接使用" />
      <CkTable columns={columns} data={tableData} />
    </>
  )
};
export default Base;
```