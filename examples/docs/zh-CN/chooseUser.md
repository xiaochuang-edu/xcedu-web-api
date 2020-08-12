## 选人组件
各个模块中，选人组件基本都会用到，所以把它放在common中打包，各自模块直接引用就可以。
  
### 引用
 
```html
<chooseUser
  ref="manager"
  v-model="form.plateAdminJson"
  :allow-write="false"
  :select-role="roles"
  :get-user="getUser"
  :get-search-list="getSearchList"
/>

<script>
  import { getChooseUserDataByParams, getSearchListByValue } from '@/api/index'

  export default {
    data () {
      return {
        roles: ['orgUser'],   // 目前只有组织用户信息可选， 后面继续添加,
        form: {
          plateAdminJson: [] // 选取的数组， 即表单提交的数组对象
        }
      }
    },
    methods: {
      getUser: getChooseUserDataByParams, // 获取ztree 数据 ， api 的方法名可自定义， getUser 为固定方法
      getSearchList: getSearchListByValue // 获取联想搜索 数据， 同上。
    }
  }
</script>
```

```javascript
  // 选人接口
export function getChooseUserDataByParams (params) {
  return axios.get('/api-base/rangeScopes', { params })
}
// 选人输入
export function getSearchListByValue (params) {
  return axios.get('/api-base/rangeScopes?type=search', { params })
}

```

### Attributes
| 参数             | 说明          | 类型      | 可选值        | 默认值  |
|-----------------|-------------- |---------- |------------ |-------- |
| v-model  | 绑定值         | Array | —  | —      |
| allow-write           |  是否可手动输入 | Boolean     | —           | —      |
| select-role | 设置选择范围	    | Array    | ['orgUser']     |  —     |