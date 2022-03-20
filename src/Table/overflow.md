---
title: 单元格溢出省略号
order: 5
group:
  path: /base
  title: 基础表格
  order: 1
---
## 单元格溢出省略号
> `showOverflow`开启所有内容溢出时显示为省略号    
> 列设置`ellipsis: true`开启该列内容溢出省略号展示    
> title：使用原生title显示
> tooltip: 使用tooltip显示

```jsx
import React from 'react';
import CkTable from 'ck-table';

const Base = () => {
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
    { name: '李四爆炸啦~李四爆炸啦~李四爆炸啦~李四爆炸啦~李四爆炸啦~李四爆炸啦~李四爆炸啦~李四爆炸啦~李四爆炸啦~李四爆炸啦~李四爆炸啦~李四爆炸啦~李四爆炸啦~', sex: '男', age: '22' },
    { name: '小红', sex: '女', age: '16' },
    { name: '王五不见啦~王五不见啦~王五不见啦~王五不见啦~王五不见啦~王五不见啦~王五不见啦~王五不见啦~王五不见啦~王五不见啦~王五不见啦~', sex: '男', age: '12' },
  ]

  return <CkTable columns={columns} data={tableData} showOverflow="tooltip" />;
};
export default Base;
```