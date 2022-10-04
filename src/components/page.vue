<template>
  <div class="page">
    <a-button @click="prev">上一页</a-button>
    <span>第<a-input style="width: 100px;" v-model="page" @blur="handleChangeSize(page)"></a-input>页</span>
    <span style="margin-left:10px;">共 {{ totalCount }} 页</span>
    <a-button @click="next">下一页</a-button>
  </div>
</template>

<script>
import { message } from 'ant-design-vue';
export default {
  name: 'page',
  props: ['totalCount', 'input'],
  data() {
    return {
      page: this.input
    }
  },
  methods: {
    handleChangeSize(input) {
      this.$emit('pageSize', input)
    },
    //上一页
    prev() {
      if (this.page > 1) {
        this.page--
      } else {
        message.info('这是首页');
        return false
      }
      this.$emit('pageSize', this.page)
    },
    //下一页
    next() {
      if (this.page < this.totalCount) {
        this.page++
      } else {
        message.info('这是最后一页');
        return false
      }
      this.$emit('pageSize', this.page)
    }
  },
  watch: {
    input(val) {
      console.log(val)
      this.page = val;
    }
  },
}
</script>

<style scoped>
.page
i {
  font-size: 20px;
  vertical-align: middle;
  color: #007DB5;
  cursor: pointer;
}

.page .el-input {
  width: 80px;
  margin: 0 8px;
}

.page .el-input .el-input__inner {
  height: 30px;
  text-align: center;
}


</style>
