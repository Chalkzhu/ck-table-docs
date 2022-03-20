---
title: 虚拟滚动
order: 1
group:
  path: /scroll
  title: 虚拟滚动
  order: 3
---
## 虚拟滚动

> 默认使用虚拟滚动
```jsx
import React from 'react';
import CkTable from 'ck-table';
import { Button } from 'antd';

const Base = () => {
  const [size, setSize] = React.useState(50);
  const columns = [
    {
      Header: '#',
      type: 'seq',
      accessor: 'seq',
      width: 200,
    },
    {
      Header: 'Name',
      accessor: 'title',
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

  const tableData = React.useMemo(() => {
    return new Array(size).fill().map((item, index) => {
      return {
        id: index + 1,
        title: index % 3 ? '这是标题' : '这是标题二',
        sex: index % 2 ? '男' : '女',
        age: Math.round(Math.random() * 100),
        address: index % 5 ? '北京' : '杭州',
        remark: '这是备注这是备注这是备注这是备注这是备注这是备注这是备注这是备注这是备注这是备注这是备注这是备注'
      };
    })
  }, [size]);

  
  const handleSize = (count) => {
    setSize(count);
  };

  return (
    <>
      <Button onClick={() => handleSize(50)}>切换 50 条数据</Button>
      <Button onClick={() => handleSize(500)} style={{margin: 12}}>切换 500 条数据</Button>
      <Button onClick={() => handleSize(1000)}>切换 1000 条数据</Button>
      <Button onClick={() => handleSize(10000)} style={{margin: 12}}>切换 10000 条数据</Button>
      <Button onClick={() => handleSize(100000)}>切换 100000 条数据</Button>
      <CkTable columns={columns} data={tableData} height={300} />
    </>
  );
};
export default Base;
```