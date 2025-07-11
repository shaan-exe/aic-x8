<script>
import Monster from './Monster.vue'
export default {
    props:["monstersHand"],
  components: {
    Monster
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
    <section id="monsterSection">
    <Monster class="Monster" v-for="monster in monstersHand" :monster="monster"></Monster>
    </section>

</template>

<style scoped>
#monsterSection{
  display: grid;
  grid-template-columns: auto;
  grid-template-rows: 1fr;

}
.Monster{
    grid-row: 1/2;
}
</style>
