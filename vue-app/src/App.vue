<script>
import heroJson from './gameJson/hero.json'
import monsterJson from './gameJson/monsterDeck.json'
import itemJson from './gameJson/itemDeck.json'
import * as math from 'mathjs';

import ItemDrawButton from './components/ItemDrawButton.vue';
import MonsterDrawButton from './components/MonsterDrawButton.vue';
import MonstersList from './components/MonstersList.vue';

// remember to register them in the components property below!

export default {
  components: {
    ItemDrawButton,
    MonsterDrawButton,
    MonstersList
  },
  data() {
    return {
      hero: heroJson,
      itemDeck: itemJson,
      monsterDeck: monsterJson,
      itemsHand: [],
      monstersHand:[]
    }
  },
  methods: {
    drawMonster() {
      let monsterCard = this.drawCard(this.monsterDeck)
      if (monsterCard) {
        let randomAction = math.randomInt(0, monsterCard.actions.length - 1)
        let action = monsterCard.actions[randomAction]
        this.hero[action.heroStatAffected] = math.evaluate(action.expression, this.hero)
        console.log(this.monstersHand)
        this.monstersHand.push(monsterCard)
        console.log(this.monstersHand)
        return monsterCard
      } else {
        return null
      }
    },
    drawItem() {
      let itemCard = this.drawCard(this.itemDeck)
      if (itemCard) {
        console.log("item", itemCard)
        this.hero[itemCard.heroStatAffected] = math.evaluate(itemCard.expression, this.hero)
        return itemCard
      } else {
        return null
      }
    },
    drawCard(deck) {
      if (deck.length !== 0) {
        const randomIndex = math.randomInt(0, deck.length - 1);
        const card = deck.splice(randomIndex, 1)[0];
        return card;
      } else {
        // deck is empty! HANDLE IT!
      }
    }
  },
  computed: {
    monstersRemaining(){
      console.log(this.monsterDeck.length)
      return this.monsterDeck.length
    },
    itemsRemaining(){
      console.log(this.itemDeck.length)
      return this.itemDeck.length
    }
  },
  mounted() {
  }
}
</script>

<template>
  <header>
    <h1></h1>
  </header>

  <main>
    <ItemDrawButton @click="drawItem" :itemsremaining="itemsRemaining"></ItemDrawButton>

    <MonsterDrawButton @click="drawMonster" :monstersremaining="monstersRemaining"></MonsterDrawButton>
    <MonstersList v-if="monstersHand" :monstersHand="monstersHand"></MonstersList>
  </main>

</template>

<style scoped></style>
