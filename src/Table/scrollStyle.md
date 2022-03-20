---
title: 滚动条样式
order: 8
group:
  path: /base
  title: 基础表格
  order: 1
---
## 滚动条样式

> 通过`height`参数设置表格的高度，当内容的宽度或高度大于表格时，自动出现滚动条    
> 默认为: '100%', 铺满父容器的高度    
> 通过css修改默认的浏览器滚动条样式，可以根据不同的浏览器特性去实现
```jsx
import React from 'react';
import CkTable from 'ck-table';
import styled from 'styled-components';

const Wrapper = styled.div`
  *::-webkit-scrollbar {
    height: 6px;
    width: 4px;
    border-radius: 6px;
  }

  *::-webkit-scrollbar-button {
    display: none;
  }

  *::-webkit-scrollbar-track {
    background-color: #eee;
  }

  *::-webkit-scrollbar-thumb {
    border-radius: 6px;
    background-color: #666;
  }
`

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
    <Wrapper>
      <CkTable columns={columns} data={tableData} stripe border={border} height={300} />
    </Wrapper>
  );
};
export default Base;
```