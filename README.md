# jsonView
Vue shows the components of JSON data
适用于Vue的Json数据展示组件，下载即用
# jsonView怎么使用
引用组件传入json数据即可展示

![image](https://github.com/kinoaa/jsonView/blob/main/jsonView.png)
```vue
<template>
  <div>
    <el-dialog :visible.sync="dialogViewCode" width="500px" title="详情" top="50px" :before-close="close" @close="onClose">
      <Json-view :json="dialogViewCodeData" />
      <div slot="footer">
        <el-button type="primary" @click="close">确定</el-button>
      </div>
    </el-dialog>
  </div>
</template>
<script>
import JsonView from '@/components/JsonView'
export default {
  components: { JsonView },
  props: {
    dialogViewCode: {
      type: Boolean,
      default: false
    },
    dialogViewCodeData: {
      type: Object,
      default: () => {}
    }
  },
  data() {
    return {
    }
  },
  watch: {
    dialogViewUserData(val) {
      if (val !== '') {
        console.log(val)
      }
    }
  },
  methods: {
    // 关闭dialog，重置数据
    onClose() {
      // this.$refs['addFrom'].resetFields()
    },
    // 关闭dialog
    close() {
      this.$emit('childMsg', { dialogViewCode: false })
    }
  }
}
</script>

<style  scoped lang='scss'>

</style>

```
