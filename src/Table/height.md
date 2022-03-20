---
title: 响应式宽高
order: 12
group:
  path: /base
  title: 基础表格
  order: 1
---
## 响应式宽高

> 通过`height`参数设置表格的高度，当内容的宽度或高度大于表格时，自动出现滚动条    
> 默认为: '100%', 铺满父容器的高度    
```jsx
import React from 'react';
import CkTable from 'ck-table';
import styled from 'styled-components';

const Base = () => {
  const [border, setBorder] = React.useState('full');
  const [width, setWidth] = React.useState('100%');
  const [height, setHeight] = React.useState(300);
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

  return (
    <>
      <button onClick={() => setWidth(500)}>宽500px</button>
      <button onClick={() => setWidth(800)} style={{margin: 12}}>宽800px</button>
      <button onClick={() => setWidth('100%')}>宽100%</button>
      <button onClick={() => setHeight(300)} style={{margin: 12}}>高300px</button>
      <button onClick={() => setHeight(600)}>高600px</button>
      <div style={{ width, height }}>
        <CkTable columns={columns} data={tableData} stripe border={border} />
      </div>
    </>
  );
};
export default Base;
```