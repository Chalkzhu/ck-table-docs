---
title: 表头分组
order: 10
group:
  path: /base
  title: 基础表格
  order: 1
---
## 表头分组

> 当数据结构比较复杂的时候，可以使用多级表头    
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
      columns: [
        {
          Header: 'First Name',
          accessor: 'firstname',
          width: 100,
          ellipsis: true,
        },
        {
          Header: 'Last Name',
          accessor: 'lastname',
          width: 100,
          ellipsis: true,
        }
      ]
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
    { firstname: '张', lastname: '三', name: '张三', sex: '男', age: '18', address: '浙江省杭州市滨江区犄角旮旯里', },
    { firstname: '李', lastname: '四', name: '李四爆炸啦~', sex: '男', age: '22', address: '浙江省杭州市滨江区犄角旮旯里' },
    { firstname: '小', lastname: '红', name: '小红', sex: '女', age: '16', address: '浙江省杭州市滨江区犄角旮旯里' },
    { firstname: '王', lastname: '五', name: '王五不见啦~', sex: '男', age: '12', address: '浙江省杭州市滨江区犄角旮旯里' },
    { firstname: '王', lastname: '五', name: '王五不见啦~', sex: '男', age: '12', address: '浙江省杭州市滨江区犄角旮旯里' },
    { firstname: '王', lastname: '五', name: '王五不见啦~', sex: '男', age: '12', address: '浙江省杭州市滨江区犄角旮旯里' },
    { firstname: '王', lastname: '五', name: '王五不见啦~', sex: '男', age: '12', address: '浙江省杭州市滨江区犄角旮旯里' },
    { firstname: '王', lastname: '五', name: '王五不见啦~', sex: '男', age: '12', address: '浙江省杭州市滨江区犄角旮旯里' },
    { firstname: '王', lastname: '五', name: '王五不见啦~', sex: '男', age: '12', address: '浙江省杭州市滨江区犄角旮旯里' },
    { firstname: '王', lastname: '五', name: '王五不见啦~', sex: '男', age: '12', address: '浙江省杭州市滨江区犄角旮旯里' },
    { firstname: '王', lastname: '五', name: '王五不见啦~', sex: '男', age: '12', address: '浙江省杭州市滨江区犄角旮旯里' },
    { firstname: '王', lastname: '五', name: '王五不见啦~', sex: '男', age: '12', address: '浙江省杭州市滨江区犄角旮旯里' },
  ];

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
      fixed: 'left',
      columns: [
        {
          Header: 'First Name',
          accessor: 'firstname',
          width: 100,
          ellipsis: true,
          fixed: 'left',
        },
        {
          Header: 'Last Name',
          accessor: 'lastname',
          width: 100,
          ellipsis: true,
          fixed: 'left',
        }
      ]
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
    { firstname: '张', lastname: '三', name: '张三', sex: '男', age: '18', address: '浙江省杭州市滨江区犄角旮旯里', },
    { firstname: '李', lastname: '四', name: '李四爆炸啦~', sex: '男', age: '22', address: '浙江省杭州市滨江区犄角旮旯里' },
    { firstname: '小', lastname: '红', name: '小红', sex: '女', age: '16', address: '浙江省杭州市滨江区犄角旮旯里' },
    { firstname: '王', lastname: '五', name: '王五不见啦~', sex: '男', age: '12', address: '浙江省杭州市滨江区犄角旮旯里' },
    { firstname: '王', lastname: '五', name: '王五不见啦~', sex: '男', age: '12', address: '浙江省杭州市滨江区犄角旮旯里' },
    { firstname: '王', lastname: '五', name: '王五不见啦~', sex: '男', age: '12', address: '浙江省杭州市滨江区犄角旮旯里' },
    { firstname: '王', lastname: '五', name: '王五不见啦~', sex: '男', age: '12', address: '浙江省杭州市滨江区犄角旮旯里' },
    { firstname: '王', lastname: '五', name: '王五不见啦~', sex: '男', age: '12', address: '浙江省杭州市滨江区犄角旮旯里' },
    { firstname: '王', lastname: '五', name: '王五不见啦~', sex: '男', age: '12', address: '浙江省杭州市滨江区犄角旮旯里' },
    { firstname: '王', lastname: '五', name: '王五不见啦~', sex: '男', age: '12', address: '浙江省杭州市滨江区犄角旮旯里' },
    { firstname: '王', lastname: '五', name: '王五不见啦~', sex: '男', age: '12', address: '浙江省杭州市滨江区犄角旮旯里' },
    { firstname: '王', lastname: '五', name: '王五不见啦~', sex: '男', age: '12', address: '浙江省杭州市滨江区犄角旮旯里' },
  ];

  return (
    <Wrapper>
      <CkTable columns={columns} data={tableData} stripe border={border} height={300} />
    </Wrapper>
  );
};
export default Base;
```