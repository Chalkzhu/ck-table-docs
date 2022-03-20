---
title: 筛选
order: 14
group:
  path: /base
  title: 基础表格
  order: 1
---
## 筛选

> 通过列设置`filter`属性可以开启筛选功能，默认提供: 'input'/'select'/'checkbox'   
```jsx
import React from 'react';
import CkTable from 'ck-table';
import 'antd/dist/antd.css';

const Base = () => {
  const columns = [
    {
      Header: '#',
      type: 'seq',
      accessor: 'seq',
      width: 200,
    },
    {
      Header: 'title',
      accessor: 'title',
      width: 200,
      ellipsis: true,
      filter: 'select',
    },
    {
      Header: 'Sex',
      accessor: 'sex',
      width: 200,
      filter: 'checkbox',
    },
    {
      Header: 'Age',
      accessor: 'age',
      width: 200,
      filter: 'input',
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
      width: 800,
      ellipsis: true,
    },
  ]

  const tableData = React.useMemo(() => {
    return new Array(100).fill().map((item, index) => {
      return {
        id: index + 1,
        title: index % 3 ? '这是标题' : '这是标题二',
        sex: index % 2 ? '男' : '女',
        age: Math.round(Math.random() * 100),
        address: index % 5 ? '北京' : '杭州',
        remark: '这是备注这是备注这是备注这是备注这是备注这是备注这是备注这是备注这是备注这是备注这是备注这是备注'
      };
    })
  }, []);

  return <CkTable columns={columns} data={tableData} stripe height={300} />;
};
export default Base;
```

> 通过`filterTypes`和`Filter`可以自定义筛选方式与筛选组件    
> 注意大小写，`filter`是筛选方式，`Filter`是筛选组件
```jsx
import React from 'react';
import CkTable from 'ck-table';

const Base = () => {
  
  // 添加额外的过滤方式: customQuery
  const filterTypes = {
    customQuery: (rows, id, filterValue) => {
      return rows.filter(row => {
        const rowValue = row.values[id];
        return rowValue === filterValue;
      });
    }
  };

  // 自定义筛选组件
  const FilterCom = ({
    column: { filterValue = [], setFilter },
  }) => {
    const onChange = (e) => {
      setFilter(e.target.value || undefined);
    };
  
    return (
      <div className="ck-table-filter-dropdown">
        <div className="ck-table-filter-header">
          <input value={filterValue || ''} placeholder="自定义的精确搜索" onChange={onChange} />
        </div>
      </div>
    )
  };

  const columns = [
    {
      Header: '#',
      type: 'seq',
      accessor: 'seq',
      width: 200,
    },
    {
      Header: 'title',
      accessor: 'title',
      width: 200,
      ellipsis: true,
      filter: 'select',
    },
    {
      Header: 'Sex',
      accessor: 'sex',
      width: 200,
      filter: 'checkbox',
    },
    {
      Header: 'Age',
      accessor: 'age',
      width: 200,
      filter: 'input',
    },
    {
      Header: 'Address',
      accessor: 'address',
      width: 300,
      ellipsis: true,
      filter: 'select',
    },
    {
      Header: '自定义筛选',
      accessor: 'custom',
      width: 300,
      filter: 'customQuery',
      Filter: (params) => <FilterCom {...params} />,
    },
    {
      Header: 'remark',
      accessor: 'remark',
      width: 800,
      ellipsis: true,
    },
  ]

  const tableData = React.useMemo(() => {
    return new Array(100).fill().map((item, index) => {
      return {
        id: index + 1,
        title: index % 3 ? '这是标题' : '这是标题二',
        sex: index % 2 ? '男' : '女',
        age: Math.round(Math.random() * 100),
        custom: index % 2 ? '自定义' : '其它',
        address: index % 5 ? '北京' : '杭州',
        remark: '这是备注这是备注这是备注这是备注这是备注这是备注这是备注这是备注这是备注这是备注这是备注这是备注'
      };
    })
  }, []);

  return <CkTable columns={columns} data={tableData} stripe height={300} filterTypes={filterTypes} />;
};
export default Base;
```