## FileUp 附件上传

文件上传和图片上传。

### 基本用法

:::demo 绑定`v-model`到一个`String`类型的变量，其中每个附件id用逗号隔开。可以使用`dir`属性指定文件上传到的服务器目录。

```html
<FileUp
  v-model="pictures"
  dir="mydir"
/>

<script>
  export default {
    data() {
      return {
        pictures: ''
      }
    }
  };
</script>
```
:::

### 图片模式

:::demo 设置`upload-type`属性，接受一个`String`，设置`image`即可开启。


```html
<FileUp
  v-model="pictures"
  upload-type="image"
  dir="mydir"
/>
<script>
  export default {
    data() {
      return {
        pictures: ''
      }
    }
  };
</script>
```
:::

### 只读状态

:::demo 设置`readonly`属性，接受一个`Boolean`，设置`true`即可不显示删除按钮以及上传附件按钮。


```html
<FileUp
  v-model="pictures"
  upload-type="image"
  dir="mydir"
  readonly
/>
<script>
  export default {
    data() {
      return {
        pictures: ''
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
| readonly  | 是否只读    | boolean   | — | false   |
| upload-type  | 附件模式或图片模式    | string   | 'file'/'image' | 'file' |
| accept  | 接受的文件类型    | string   | — | — |
| accept-tips  | 文字提示    | string   | — | — |

### Events
| 事件名称      | 说明    | 回调参数      |
|---------- |-------- |---------- |
| input  | value发生变化时的回调函数    | 新value值 |

### Methods
| 方法名 | 说明 | 参数 |
| ---- | ---- | ---- |
| validateFinished | 查询是否还有未完成的上传 | - |
