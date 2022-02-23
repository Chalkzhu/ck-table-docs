---
title: 序号
order: 3
group:
  path: /base
  title: 基础表格
  order: 1
---
## 序号

> 设置: type="seq" 开启序号列
> 默认为small,对应表格行高度: 64px/48px/36px

```tsx
import React from 'react';
import CkTable from 'ck-table';

const Base = () => {
  const columns = [
    {
      title: '#',
      type: 'seq',
      accessor: 'seq',
      width: 100,
    },
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

  return <CkTable columns={columns} data={tableData} />;
};
export default Base;
```