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
    <Monster v-for="monster in monstersHand" :monster="monster"></Monster>

</template>

<style scoped></style>
