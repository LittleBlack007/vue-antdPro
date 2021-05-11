
<template>
  <VoteShow :seats="this.seats" @onSubmit='onSubmit'/>
</template>

<script>
import VoteShow from './components/vote-show'
export default ({
  name:'Vote',
  components:{
    VoteShow
  },
  data(){
    return {
      mySeats:[],
      seats:[]

    }
  },
  computed:{
    
  },
  methods:{
    initSeat(){
      let arr =  [9,16]
      let seatArr = []
      let seatCol = []
      for(let i=0;i<arr[1];i++){
        seatCol.push(0);
      }
      console.log(seatCol)
      for(let i=0;i<arr[0];i++){
        seatArr.push(seatCol);
      }
      console.log(seatArr)
      return seatArr;
    },
    onSubmit(result){
      console.log(result)
    }
  },
  created(){
    this.seats = this.initSeat();
  }



})
</script>

<style lang="less" scoped>
.container{
  width: 100%;
  height: 100%;
  min-height: 800px;
  background-color: pink;
  input{
    width:30px;
    height: 30px;
    margin: 5px;
  }
}
</style>
