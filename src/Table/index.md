---
title: 基础
order: 1
group:
  path: /base
  title: 基础表格
  order: 1
---
## 基础表格

> 与传统表格使用方式一样，使用非常简单！
```jsx
import React from 'react';
import CkTable from 'ck-table';

const Base = () => {
  const [align, setAlign] = React.useState('left');
  const columns = [
    {
      Header: 'Name',
      accessor: 'name',
      width: 100,
      align,
    },
    {
      Header: 'Sex',
      accessor: 'sex',
      width: 100,
      align,
    },
    {
      Header: 'Age',
      accessor: 'age',
      width: 100,
      align,
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
      <button onClick={() => setAlign('left')}>居左</button>
      <button onClick={() => setAlign('center')} style={{margin: 12}}>居中</button>
      <button onClick={() => setAlign('right')}>居右</button>
      <CkTable columns={columns} data={tableData} />
    </>
  )
};
export default Base;
```
 
 
> 使用rowConfig.isHover属性启用hover行高亮
```jsx
import React from 'react';
import CkTable from 'ck-table';

const Base = () => {
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
      <CkTable columns={columns} rowConfig={{ isHover: true }} data={tableData} />
    </>
  )
};
export default Base;
```