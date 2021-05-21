<!-- 测试activated生命周期 -->
<template>
  <div>
    <div>
      <button @click="currentView = 'A'">a</button>
      <button @click="currentView = 'B'">b</button>
    </div>
    <div>
      <keep-alive>
        <component :is="currentView"></component>
      </keep-alive>
    </div>
  </div>
</template>

<script>
import A from './a.vue';
import B from './b.vue';
export default {
  components: {
    A,B
  },
  data() {
    return {
      currentView: "B",
      showModal: false
    }
  },
  computed: {},
  //监控data中的数据变化
  watch: {},
  //方法集合
  methods: {},
  //生命周期 - 创建完成（可以访问当前this实例）
  created() {},
  //生命周期 - 挂载完成（可以访问DOM元素）
  mounted() {},
}
</script>

<style lang='stylus' rel='stylesheet/stylus'>

</style>