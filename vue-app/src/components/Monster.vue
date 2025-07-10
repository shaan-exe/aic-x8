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
        <h1>{{monster.name}}</h1>
        <p>{{ monster.description }}</p>
    </div>
    

</template>

<style scoped>
div{
    border: 1.5px solid black;
    border-radius: 5%;
    min-height: 300px;
    width:12vw;
    padding:10px;
    margin:10px;
}
</style>
