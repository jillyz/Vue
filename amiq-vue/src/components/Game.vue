<template>
  <div class="game">
    <div class="wrap">
      <img class="wrap-item topic" alt="Vue logo" src="../assets/game/topic.jpg">
      <div class="wrap-item card-list">
        <ul>
          <li v-for="(item,index) in 12" :key="index" @click="chooseItem(parseInt(`${index}`) + 1)">
            <GameCard :num="parseInt(`${index}`) + 1" />
          </li>
        </ul>
      </div>
    </div>
    <div class="option-grid">
      <ul>
        <li v-for="(item,index) in 12" :key="index" @click="putItem(`${chooseNum}`)" >
          <GameOption :order="parseInt(`${index}`) + 1" :putNum="parseInt(`${putNum}`)" :putOrder="parseInt(`${index}`) + 1" />
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
import GameCard from '../components/GameCard.vue';
import GameOption from '../components/GameOption.vue';

export default {
  name: 'Game',
  components: {
    GameCard,
    GameOption
  },
  props: {
    chooseNum: Number,
    putNum: Number,
    putOrder: Number,
  },
  methods:{
    chooseItem: function( n ){
      this.chooseNum = n;
      console.log('chooseItem', this.chooseNum )
    },
    putItem: function(n) {
      this.putNum = n;
      console.log('putNum', this.putNum )
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .game {
    position: relative;
  }
  .game {
    display: table;
    margin: 0 auto;
  }
  .wrap-item {
    float: left;
  }
  .card-list {
    width: calc((100vh/6) * 2);
    background-color: #ffc630;
  }
  .card-list ul,
  .card-list li {
    margin: 0;
    padding: 0;
    list-style: none;
  }
  .card-list li {
    display: inline-block;
    margin: 1vh;
    width: 14.5vh;
    height: 14.5vh;
    line-height: 14.5vh;
    background-color: #F4EED4;
    color: #333;
    font-size: 3vh;
    border-radius: 1vh;
  }
  .topic {
    height: 100vh;
  }
  .card-list {
    float: right;
  }
  .choosed {
    opacity: .2;
  }
  .option-grid {
    position: absolute;
    bottom: 2.5vh;
    width: 100vh;
    left: -6.2vh;
  }
  .option-grid li {
    display: inline-block;
    width: 14.5vh;
    height: 14.5vh;
    border: 3px solid #ffc630;
    margin-bottom: -6px;
    margin-left: -3pX;
  }
</style>
