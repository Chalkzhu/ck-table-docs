---
title: 完整功能
order: 17
group:
  path: /base
  title: 基础表格
  order: 1
---
## 完整示例

> 通过列设置`Cell`,格式化内容
```jsx
import React from 'react';
import CkTable from 'ck-table';
import { Button, Checkbox } from 'antd';
import 'antd/dist/antd.css';

const Base = () => {
  const columns = [
    {
      Header: 'checkbox',
      type: 'checkbox',
      accessor: 'checkbox',
      width: 80,
      maxWidth: 80,
      fixed: 'left',
    },
    {
      Header: '#',
      type: 'seq',
      accessor: 'seq',
      width: 80,
      maxWidth: 80,
      fixed: 'left',
    },
    {
      Header: 'title',
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
      width: 300,
      ellipsis: true,
      filter: 'select',
    },
    {
      Header: 'remark',
      accessor: 'remark',
      width: 300,
      ellipsis: true,
    },
  ];

  const tableData = React.useMemo(() => {
    return new Array(100).fill().map((item, index) => {
      return {
        id: index + 1,
        title: index % 3 ? '这是标题' : '这是标题二',
        sex: index % 2 ? '男' : '女',
        age: Math.round(Math.random() * 100),
        custom: index % 2 ? '自定义' : '其它',
        address: index % 5 ? '北京' : '杭州',
        remark: '这是备注这是备注这是备注这是备注这是备注这是备注这是备注这是备注这是备注这是备注这是备注这是备注这是备注这是备注这是备注这是备注这是备注这是备注这是备注这是备注这是备注这是备注这是备注这是备注'
      };
    })
  }, []);

  
  const config = {
    rowConfig: {
      isHover: true,
    },
    sortConfig: {
      trigger: 'cell',
    },
    checkboxConfig: {
      Control: (resetProps) =>  <Checkbox {...resetProps} />,
    },
    toolbar: { setting: true },
    size: "small",
    resizable: true,
    stripe: true,
    showOverflow: 'tooltip',
    sortChange: ({id, isSortedDesc, isSorted}) => {
      const order = isSortedDesc ? 'desc' : isSorted ? 'asc' : null;
      console.log('sortChange', id, order);
    }
  }

  return <CkTable columns={columns} data={tableData} height={300} {...config} />;
};
export default Base;
```
