<template>
  <div class="box">
    <div>我是a组件</div>
    <div>
      <button @click="show = !show">切换</button>
    </div>
    <div v-if="show">show</div>
    <div v-if="!show">hide</div>
  </div>
</template>

<script>
export default {
  name:"A",
  data(){
    return {
      show: true,
    }
  },
  methods:{
  },
  beforeMount(){
    console.log("beforeMounted");
  },
  mounted(){
    console.log("mounted");
  },
  beforeCreate(){
    console.log("beforeCreate");
  },
  created(){
    console.log("created");
  },
  activated(){
    console.log("activated");
  },
  deactivated(){
    console.log("deactivated")
  }

}
</script>

<style>

</style>