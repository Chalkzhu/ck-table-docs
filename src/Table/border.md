---
title: 边框
order: 7
group:
  path: /base
  title: 基础表格
  order: 1
---
## 边框

> 通过设置`border`参数 显示你需要的边框

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
    { name: '李四爆炸啦~', sex: '男', age: '22' },
    { name: '小红', sex: '女', age: '16' },
    { name: '王五不见啦~', sex: '男', age: '12' },
  ]

  return (
    <>
      <button onClick={() => setBorder('full')}>显示默认边框</button>
      <button onClick={() => setBorder('outer')} style={{margin: 12}}>外边框</button>
      <button onClick={() => setBorder('inner')}>内边框</button>
      <button onClick={() => setBorder('none')} style={{margin: 12}}>无边框</button>
      <CkTable columns={columns} data={tableData} stripe border={border} />
    </>
  );
};
export default Base;
```