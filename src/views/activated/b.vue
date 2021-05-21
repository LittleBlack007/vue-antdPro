<template>
  <div class="box">
    <div>我是b组件</div>
    <div>
      <button @click="show = !show">切换</button>
    </div>
    <div v-if="show">show</div>
    <div v-if="!show">hide</div>
  </div>
</template>

<script>
export default {
  name:"B",
  data(){
    return {
      show: true,
    }
  },
  methods:{
  },
  beforeMount(){
    console.log("B-beforeMounted");
  },
  mounted(){
    console.log("B-mounted");
  },
  beforeCreate(){
    console.log("B-beforeCreate");
  },
  created(){
    console.log("B-created");
  },
  activated(){
    console.log("B-activated");
  },
  deactivated(){
    console.log("B-deactivated")
  }

}
</script>

<style>

</style>