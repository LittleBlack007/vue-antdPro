
<template>
  <div class='container' @click="onClick">
    <div v-for='(row,index) in this.seats'>
      <input v-for='(col,i) in row' type="checkbox" :id="[index,i]" :checked='col === 1'/>
    </div>
  </div>
</template>

<script>

export default ({
  name:'VoteShow',

  data(){
    return {
      allSeat:[9,16],
      selectedSeats: [],

    }
  },
  props:{
    seats:Array,
    onSubmit:Function
  },
  computed:{
    
  },
  methods:{
    onClick(e){
      console.log(e.target.type)
      if(e.target.type === 'checkbox'){
        let position = e.target.id.split(',');
        console.log(parseInt(position[0]),parseInt(position[1]))
        this.seats[parseInt(position[0])][parseInt(position[1])] = e.target.checked?1:0;
        if(e.target.checked){
          this.selectedSeats.push(e.target.id);
        }
        else{
          let index = this.selectedSeats.indexOf(e.target.id);
          this.selectedSeats.splice(index,1);
        }
      }
      let result = {}
      result.selectedSeats = this.selectedSeats;
      result.seats = this.seats;
      this.$emit('onSubmit',result)
    },
    initSeat(){
      let arr =  this.allSeat
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
  },
  mounted(){
    if(this.seats.length > 0){
      this.seats.forEach((item,index) => {
        item.forEach((col,i) => {
          if(col === 1){
            this.selectedSeats.push(''+index+i)
          }
        })
      })
    }
    console.log('mounted',this.seats)
  },

  setup() {
    
  },



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
