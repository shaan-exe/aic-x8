<script>
 
export default {
    props:["hero"],
  components: {
  },
  data() {
    return {
    }
  },
  methods: {
  },
  computed: {
  },
  mounted() {
  }
}
</script>

<template>
    <div>
        <h3>{{hero.name}}</h3>
        <p>{{ hero.description }}</p>
        <img :src="hero.portraitURL" />
        
    </div>
    

</template>

<style scoped>
div{
    color:rgb(128, 110, 7);
    border: 3px solid gold;
    background-color: rgba(99, 85, 4, 0.127);
    border-radius: 5%;
    min-height: 325px;
    width:10vw;
    padding:10px;
 
    text-align: center;
}
div img{
    padding:5px;
  
    border-radius: 5%;
    width:50%;
}
</style>
