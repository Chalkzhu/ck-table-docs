---
title: 尺寸
order: 2
group:
  path: /base
  title: 基础表格
  order: 1
---
## 基础表格

> 通过设置`size`参数调整表格大小，默认为small   
> 可以设置大小尺寸： large/small/mini,对应表格行高度: 64px/48px/36px

```tsx
import React from 'react';
import CkTable from 'ck-table';

const Base = () => {
  const [size, setSize] = React.useState('small');

  const columns = [
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

  return (
    <>
      <button onClick={() => setSize('large')}>大号</button>
      <button onClick={() => setSize('small')} style={{margin: 12}}>中号</button>
      <button onClick={() => setSize('mini')}>小号</button>
      <CkTable columns={columns} data={tableData} size={size} />
    </>
  )
};
export default Base;
```