<template>
  <el-tree :data="data" :props="defaultProps" @node-click="handleNodeClick"></el-tree>
</template>

<script>

  export default {
    //import引入的组件需要注入到对象中才能使用",
    components: {},
    data() {
      return {
        data: [],
        defaultProps: {
          children: "children",
          label: "label"
        }
      };
    },
    //监听属性 类似于data概念",
    computed: {},
    //监控data中的数据变化",
    watch: {},
    //方法集合",
    methods: {
      handleNodeClick(data) {
        console.log(data);
      }
    },
    getMenus() {
      this.$http({
        url: this.$http.adornUrl('/product/category/list/tree'),
        method: 'get',
      }).then((data) => {
        console.log("成功获取到菜单数据" + data)
      })
    },
    //生命周期 - 创建之前",数据模型未加载,方法未加载,html模板未加载
    beforeCreate() {
    },

    //生命周期 - 创建完成（可以访问当前this实例）",数据模型已加载，方法已加载,html模板已加载,html模板未渲染
    created() {
      this.getMenus()
    },
    //生命周期 - 挂载之前",html模板未渲染
    beforeMount() {

    },

    //生命周期 - 挂载完成（可以访问DOM元素）",html模板已渲染
    mounted() {

    },

    //生命周期 - 更新之前",数据模型已更新,html模板未更新
    beforeUpdate() {

    },
    //生命周期 - 更新之后",数据模型已更新,html模板已更新
    updated() {

    },
    //生命周期 - 销毁之前",
    beforeDestroy() {

    },
    destroyed() {

    },
    //生命周期 - 销毁完成",
    //如果页面有keep-alive缓存功能，这个函数会触发",
    activated() {

    },
  }


  // "http-get请求": {
  //   "prefix": "httpget",
  //     "body": [
  //     "this.\({",
  //     "url: this.\\$http.adornUrl(''),",
  //     "method: 'get',",
  //     "params: this.\\$http.adornParams({})",
  //     "}).then(({ data }) => {",
  //     "})"
  //   ],
  //     "description": "httpGET请求"
  // },
  // "http-post请求": {
  //   "prefix": "httppost",
  //     "body": [
  //     "this.\({",
  //     "url: this.\\$http.adornUrl(''),",
  //     "method: 'post',",
  //     "data: this.\\$http.adornData(data, false)",
  //     "}).then(({ data }) => { });"
  //   ],
  //     "description": "httpPOST请求"
  // }
  // }

</script>

<style>

</style>
