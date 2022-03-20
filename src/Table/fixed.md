---
title: 固定列
order: 9
group:
  path: /base
  title: 基础表格
  order: 1
---
## 固定列

> 通过`fixed: 'left'|'right'`来启用固定列    
> 当横向内容过多时，将列固定在左右两侧    
> 采用了`position: sticky`实现固定列
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

  return (
    <Wrapper>
      <CkTable columns={columns} data={tableData} stripe border={border} height={300} />
    </Wrapper>
  );
};
export default Base;
```

> 在列宽足够的情况下的展示状态
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
      width: 200,
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