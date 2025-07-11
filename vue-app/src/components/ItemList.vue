<script>

import Item from './Item.vue'
export default {
    props:["itemsHand"],
  components: {
    Item
  },
  data() {
    return {
    }
  },
  methods: {
   emitExpression(exp){
    this.$emit('updateHero', exp); 
    console.log('step 2',exp)}
   },
  
  computed: {
  },
  mounted() {
  }
}
</script>

<template>
    <section id="itemSection">
    <Item @updateStats="(exp)=>{emitExpression(exp)}" class="Item" v-for="item in itemsHand" :item="item"></Item>
    
</section>  

</template>

<style scoped>
#itemSection{
  display: grid;
  grid-template-columns: auto;
  grid-template-rows: 1fr;
 
}
.Item{
    grid-row: 1/2;
}
</style>
