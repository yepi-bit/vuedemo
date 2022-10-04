<template>
  <div class="searchList">
    <Page :totalCount="totalCount" :input="currentPage" v-on:pageSize="changPageSize"></Page>
  </div>
</template>

<script>
import Page from "../components/page.vue"

export default {
  name: 'SearchPage',
  components: {
    Page
  },
  data() {
    return {
      totalCount: 10,//数据总条目数
      currentPage: 2,//当前页
    }
  },
  methods: {
    changPageSize(input) {
      console.log(input)
      // ...数据处理
    },
  }
}
</script>

<style scoped>

</style>
