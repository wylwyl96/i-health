<template>
  <div id="diet">
    <h1 v-if="isActive">Diet Suggestion</h1>
    <div>
      <b-button block variant="primary" @click="filterFood('Protein')"
        >Protein</b-button
      >
      <b-button block variant="dark" @click="filterFood('Carbohydrates')"
        >Carbohydrates</b-button
      >
      <b-button block variant="warning" @click="filterFood('Fats')">Fats</b-button>
      <b-button block variant="info" @click="filterFood('Vitamins')"
        >Vitamins</b-button
      >
      <b-button block variant="danger" @click="filterFood('Minerals')"
        >Minerals</b-button
      >
      <b-button block variant="secondary" @click="filterFood('Water')"
        >Water</b-button
      >
    </div>
    <b-list-group v-if="selected.length > 0">
      <b-list-group-item v-for="(food, index) in selected" :key="index">{{
        food.foodName
      }}</b-list-group-item>
    </b-list-group>
  </div>
</template>

<script>
export default {
  name: "Demo",
  data() {
    return {
      isActive: true,
      selected: [],
      foods: [
        {
          foodID: 1,
          foodName: "Egg",
          nutrient: "Protein",
        },
        {
          foodID: 2,
          foodName: "Fish",
          nutrient: "Protein",
        },
        {
          foodID: 3,
          foodName: "Beans",
          nutrient: "Carbohydrates",
        },
        {
          foodID: 4,
          foodName: "Fiber-rich vegetables",
          nutrient: "Carbohydrates",
        },
        {
          foodID: 5,
          foodName: "Nuts",
          nutrient: "Fats",
        },
        {
          foodID: 6,
          foodName: "Vegetable oils",
          nutrient: "Fats",
        },
        {
          foodID: 7,
          foodName: "Vegetables",
          nutrient: "Vitamins",
        },
        {
          foodID: 8,
          foodName: "Fruits",
          nutrient: "Vitamins",
        },
        {
          foodID: 9,
          foodName: "Beans",
          nutrient: "Minerals",
        },
        {
          foodID: 10,
          foodName: "Mushrooms",
          nutrient: "Minerals",
        },
        {
          foodID: 11,
          foodName: "Fruits",
          nutrient: "Water",
        },
        {
          foodID: 12,
          foodName: "Vegetables",
          nutrient: "Water",
        },
      ],
    };
  },
  methods: {
    filterFood(type) {
      this.selected = this.foods.filter((food) => {
        return food.nutrient == type;
      });
    },
  },
};
</script>
<style scoped>
h1 {
  margin: 20px;
  font-size: 1.8rem;
  color: #070c51;
}
</style>