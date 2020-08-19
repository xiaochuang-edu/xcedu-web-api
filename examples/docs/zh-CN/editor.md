## Editor 富文本编辑器

富文本编辑器。

### 基本用法

:::demo 绑定`v-model`到一个`String`类型的变量。

```html
<Editor v-model="content" />

<script>
  export default {
    data() {
      return {
        content: ''
      }
    }
  };
</script>
```
:::

### 禁用状态

:::demo 设置`disabled`属性，接受一个`Boolean`，设置`true`即可禁用。


```html
<Editor v-model="content" disabled />
<script>
  export default {
    data() {
      return {
        content: ''
      }
    }
  };
</script>
```
:::


### Attributes

| 参数      | 说明    | 类型      | 可选值       | 默认值   |
|---------- |-------- |---------- |-------------  |-------- |
| value / v-model | 绑定值 | string | — | '' |
| disabled  | 是否禁用    | boolean   | — | false   |

### Events
| 事件名称      | 说明    | 回调参数      |
|---------- |-------- |---------- |
| input  | value发生变化时的回调函数    | 新value值 |

### Methods
| 方法名 | 说明 | 参数 |
| ---- | ---- | ---- |
| - | - | - |
