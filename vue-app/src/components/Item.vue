<script>
 
export default {
    props:["item"],
  components: {
  },
  data() {
    return {
    }
  },
  methods: {
    computeItemExpression(){
        console.log("step 1")
    this.$emit('updateStats', this.item.expression)
}
  },
  computed: {
  },
  mounted() {
  }
}
</script>

<template>
    
    <div >
        <h3>{{item.name}}</h3>
        <p>{{ item.description }}</p>
        <button @click="computeItemExpression">Use Item</button>
        
    </div>

    

</template>

<style scoped>
div{
    
    color:rgb(44, 109, 109);;
    border: 3px solid rgb(44, 109, 109);
    background-color: rgba(44, 109, 109, 0.115);
    border-radius: 5%;
    min-height: 325px;
    width:10vw;
    padding:10px;
    margin:10px;
    text-align: center;
}
div:hover{
    pointer:cursor;
    
}
div img{
    padding:5px;
    border: 3px solid black;
    border-radius: 5%;
    width:50%;
}
</style>
