<script>
  export default {
    name: "Foods",
    data() {
      return {
        foods: [
          { name: 'Apples', desc: 'Apples are a type of fruit that grow on trees.', favorite: true},
          { name: 'Pizza', desc: 'Pizza has a bread base with tomato sauce, cheese, and toppings on top.', favorite: false},
          { name: 'Rice', desc: 'Rice is a type of grain that people like to eat.', favorite: false},
          { name: 'Fish', desc: 'Fish is an animal that lives in water.', favorite: true},
          { name: 'Cake', desc: 'Cake is something sweet that tates good.', favorite: false}
        ]
      }
    },
    methods: {
      recieveEmit(foodId) {
        let foundFood = this.foods.find( x => x.name === foodId)
        foundFood.favorite = !foundFood.favorite
      }
    }
  }
</script>

<template>
  <div class="w3-container">
    <h1>Foods</h1>
    <div class="w3-container wrapper">
      <food-item
        v-for="x in foods"
        :key="x.name"
        :food-name="x.name"
        :food-desc="x.desc"
        :is-favorite="x.favorite"
        @toggle-favorite="recieveEmit"
      ></food-item>
    </div>
  </div>
</template>

<style>
  .wrapper {
    display: flex;
    flex-wrap: wrap;
  }
  .wrapper > div {
    flex-basis: 200px;
    margin: 10px;
    padding: 10px;
    border: dashed black 1px;
    background-color: lightgreen;
  }
</style>