## API

### 属性

| 属性          | 类型                     | 说明                                                               | 默认值                    |
| ------------- | ------------------------ | ------------------------------------------------------------------ | ------------------------- |
| value         | Number \| String \| Date | 日历当前选中的日期                                                 | null                      |
| year          | Number                   | 日历当前所在的年份                                                 | new Date().getFullYear()  |
| month         | Number                   | 日历当前所在的月份，可选值为 1 ~ 12                                | new Date().getMonth() + 1 |
| week-days     | Array                    | 日历头部的星期数显示的标签，需传入一个大小为 7 的数组              | null                      |
| week-start    | Number                   | 设置日历每星期的第一天，可选值为 0 ~ 7，其中 0 为星期天            | 0                         |
| today         | Number \| String \| Date | 设置日历的今天日期                                                 | new Date()                |
| disabled-date | Function                 | 是日历的禁用日期，接收当前需要判断的日期作为参数，返回 true 则禁用 | () => false               |

### 事件

| 事件      | 说明                                           | 参数 |
| --------- | ---------------------------------------------- | ---- |
| on-select | 在日历选中的日期变化时触发，返回当前选中的日期 | date |

### 插槽

| 名称    | 说明                                                                                                  |
| ------- | ----------------------------------------------------------------------------------------------------- |
| header  | 日历的头部内容插槽，使用后将替换日历的整个头部                                                        |
| title   | 日历的标题内容插槽                                                                                    |
| week    | 日历星期数内容的插槽，通过 v-slot 接收一个 `{ label, index, week }` 对象                              |
| content | 日历单元格内容插槽，通过 v-slot 接收一个 `{ selected, date, isPrev, isNext, isToday, disabled }` 对象 |