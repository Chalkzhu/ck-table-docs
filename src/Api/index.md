---
title: Api
order: 9
group:
  path: /api
  title: Api
  order: 9
---

## CkTable

| 参数           | 说明           | 类型           | 可选                         | 默认值  |
| -------------- | -------------- | -------------- | ---------------------------- | ------- |
| data           | 行数据         | Array          | []                           | []      |
| columns        | 列数据         | Array          | []                           | []      |
| size           | 尺寸: 64/48/36 | String         | 'large'/'small'/'mini'       | 'small' |
| resizable      | 是否可调整列宽 | Boolean        | true/false                   | false   |
| stripe         | 斑马条纹       | Boolean        | true/false                   | false   |
| height         | 表格高度       | Number         | Number/'100%'                | '100%'  |
| showOverflow   | 溢出省略       | Boolean/String | true/false/'tooltip'/'title' | false   |
| toolbar        | 工具栏         | Object         | setting/                     |         |
| showFooter     | 是否显示表尾   | Boolean        | true/false                   | false   |
| filterTypes    | 过滤拓展       | Object         |                              |         |
| rowConfig      | 行配置         | Object         |                              |         |
| sortConfig     | 排序配置       | Object         |                              |         |
| columnConfig   | 列配置         | Object         |                              |         |
| checkboxConfig | 复选框配置     | Object         |                              |         |



## Column

| 参数     | 说明             | 类型       | 可选                        | 默认值 |
| -------- | ---------------- | ---------- | --------------------------- | ------ |
| title    | 标题             | String/Jsx |                             | ''     |
| Cell     | 单元格           | String/Jsx |                             | ''     |
| Footer   | 页脚             | String/Jsx |                             | ''     |
| accessor | 键值             | String     |                             | ''     |
| width    | 宽度             | Number     |                             | 250    |
| minWidth | 最小宽度         | Number     |                             | 60     |
| maxWidth | 最大宽度         | Number     |                             | -      |
| fixed    | 固定位置         | String     | 'left'/'right'              |        |
| type     | 基础类型         | String     | 'checkbox'/'seq'            |        |
| visible  | 默认是否显示     | Boolean    | true/false                  | true   |
| sort     | 是否启用排序     | Boolean    | true/false                  | fasle  |
| filter   | 过滤类型         | String     | 'checkbox'/'select'/'input' |        |
| Filter   | 自定义过滤器     | JSX        | checkbox                    |        |
| ellipsis | 是否超出省略代替 | Boolean    | true/false                  | false  |
| align    | 对齐方式         | String     | 'left'/'center'/'right'     |        |
|          |                  |            |                             |        |



## rowConfig

> 行配置

| 参数    | 说明             | 类型    | 可选       | 默认值 |
| ------- | ---------------- | ------- | ---------- | ------ |
| isHover | 是否鼠标移入高亮 | Boolean | true/false | false  |
|         |                  |         |            |        |

## sortConfig

> 排序配置

| 参数    | 说明     | 类型   | 可选             | 默认值    |
| ------- | -------- | ------ | ---------------- | --------- |
| trigger | 触发方式 | String | 'default'/'cell' | 'default' |
|         |          |        |                  |           |

## columnConfig

> 列配置



## checkboxConfig

> 复选框配置

### Control

> 复选框组件配置

```js
// Control
自定义复选组件，接收参数
(props) => <Component {...props} />,
// 参数
props: {
  checked: true, // 是否选中
  indeterminate: false, // 是否半选
  onChange: (), // 触发事件
  style: {cursor: 'pointer'}, // 样式
}
```

## filterTypes

> 过滤方式拓展

```js
/* filterTypes
  自定义过滤类型及方法，为了避免不必要的渲染，请使用memoized
  默认内置模糊文本和数组过滤：text/fuzzyText/checkbox
  接收参数：行数据/列键值/筛选的内容
*/
filterTypes: {
    methodName: (rows, columnAccessor, filterValue) => Boolean
}

/*
  filter: 过滤类型
  如果使用自定义 `filterTypes`, 需要与 `Filter` 配合使用
*/

/*
  Filter: 自定义筛选框
*/
Filter: ({column: { filterValue = [], setFilter, preFilteredRows, id }}) => JSX

// 使用
{
    Header: '自定义筛选',
    accessor: 'custom',
    filter: 'methodName',
    Filter: () => <Component />
}
```



## Event

> 触发的事件

| 参数       | 说明     | 类型 | 可选 | 默认值  |
| ---------- | -------- | ---- | ---- | ------- |
| sortChange | 排序触发 |      |      | $column |
|            |          |      |      |         |

## Methods

> 方法

| 参数               | 说明                                       | 返回类型 | 可选 | 默认值 |
| ------------------ | ------------------------------------------ | -------- | ---- | -----: |
| getCheckboxRecords | 用于 type=checkbox<br />获取当前选中的数据 | Array    |      |        |
| tableInstance      | 返回实例属性，用于拓展自定义功能           | Object   |      |        |