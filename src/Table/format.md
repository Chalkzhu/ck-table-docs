---
title: 格式化内容
order: 16
group:
  path: /base
  title: 基础表格
  order: 1
---
## 格式化内容

> 通过列设置`Cell`,格式化内容
```jsx
import React from 'react';
import CkTable from 'ck-table';

const Base = () => {
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
      Header: '格式化年龄',
      accessor: 'age',
      width: 200,
      Cell: ({age}) => {
        return age % 2 ? '我被格式化了' : age;
      },
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
    { name: '王五不见啦~', sex: '男', age: '5', address: '浙江省杭州市滨江区犄角旮旯里' },
    { name: '王五不见啦~', sex: '男', age: '12', address: '浙江省杭州市滨江区犄角旮旯里' },
    { name: '王五不见啦~', sex: '男', age: '13', address: '浙江省杭州市滨江区犄角旮旯里' },
    { name: '王五不见啦~', sex: '男', age: '12', address: '浙江省杭州市滨江区犄角旮旯里' },
    { name: '王五不见啦~', sex: '男', age: '15', address: '浙江省杭州市滨江区犄角旮旯里' },
    { name: '王五不见啦~', sex: '男', age: '12', address: '浙江省杭州市滨江区犄角旮旯里' },
    { name: '王五不见啦~', sex: '男', age: '17', address: '浙江省杭州市滨江区犄角旮旯里' },
    { name: '王五不见啦~', sex: '男', age: '12', address: '浙江省杭州市滨江区犄角旮旯里' },
    { name: '王五不见啦~', sex: '男', age: '12', address: '浙江省杭州市滨江区犄角旮旯里' },
  ]

  return <CkTable columns={columns} data={tableData} height={300} />;
};
export default Base;
```

> 支持标准数据结构，Html标签
```jsx
import React from 'react';
import CkTable from 'ck-table';

const Base = () => {
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
      Header: 'Html',
      accessor: 'img',
      width: 200,
    },
    {
      Header: '格式化年龄',
      accessor: 'age',
      width: 200,
      Cell: ({age}) => {
        return age % 2 ? '我被格式化了' : age;
      },
    },
    {
      Header: 'Address',
      accessor: 'address',
      width: 800,
      ellipsis: true,
    },
  ]

  
  const tableData = React.useMemo(() => {
    return new Array(100).fill().map((item, index) => {
      return {
        id: index + 1,
        name: index % 3 ? '张三' : '李四',
        sex: index % 2 ? '男' : '女',
        age: Math.round(Math.random() * 100),
        img: <img src='http://www.wuliwu.top/logo.png' width={36} alt="我是图片" />,
        custom: index % 2 ? '自定义' : '其它',
        address: index % 5 ? '北京' : '杭州',
        remark: '这是备注这是备注这是备注这是备注这是备注这是备注这是备注这是备注这是备注这是备注这是备注这是备注这是备注这是备注这是备注这是备注这是备注这是备注这是备注这是备注这是备注这是备注这是备注这是备注'
      };
    })
  }, []);

  return <CkTable columns={columns} data={tableData} height={300} />;
};
export default Base;
```