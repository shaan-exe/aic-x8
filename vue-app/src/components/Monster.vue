<script>
 
export default {
    props:["monster"],
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
        <h3>{{monster.name}}</h3>
        <p>{{ monster.description }}</p>
        <img :src="monster.portraitURL" />
    </div>
    

</template>

<style scoped>
div{
    color:rgb(175, 60, 42);
    border: 3px solid rgb(175, 60, 42);
    background-color: rgb(175, 60, 42, 0.115);
    border-radius: 5%;
    min-height: 325px;
    width:10vw;
    padding:10px;
    margin:10px;
    text-align: center;
}
div img{
    padding:5px;
    
    border-radius: 5%;
    width:50%;
}
</style>
