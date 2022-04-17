<template>
  <div class="container">
    <select class="selector" v-model="criteria">
      <option value="Criteria">Criteria</option>
      <option
        v-for="_criteria in criterias"
        :key="_criteria"
        :value="_criteria"
      >
        {{ _criteria }}
      </option>
    </select>
    <select class="selector" v-if="criteria !== 'Criteria'" v-model="type">
      <option value="Type">Type</option>
      <option
        v-for="_type in typesByCriteria[criteria]"
        :key="_type"
        :value="_type"
      >
        {{ _type }}
      </option>
    </select>
  </div>
</template>

<script>
export default {
  emits: ["selected"],
  data() {
    return {
      criterias: ["Color", "Laminate", "Parquet", "Tiles", "Wallpaper"],
      criteria: "Criteria",
      typesByCriteria: {
        Criteria: [],
        Color: ["Blue", "Brown", "Green", "Red", "Yellow"],
        Laminate: [
          "Beige",
          "Blue",
          "Dark Brown",
          "Gray",
          "Light Brown",
          "White",
        ],
        Parquet: ["Brown", "Gray", "Orange", "White", "Yellow"],
        Tiles: ["Beige", "Colorful", "Matt", "Polished", "White", "Wooden"],
        Wallpaper: ["Bricks", "Flowers", "Kids", "Photos", "Vintage"],
      },
      type: "Type",
    };
  },
  watch: {
    criteria(_new, _old) {
      this.type = "Type";
    },
    type(_new, _old) {
      if (_new !== "Type") this.$emit("selected", this.criteria, _new);
      else this.$emit("selected", undefined, undefined);
    },
  },
};
</script>

<style scoped>
.selector {
  padding: 0 0.5rem;
  height: 2.4rem;
  font-size: 1.5rem;
  border-radius: 20px;
  border: 2px solid white;
  background-color: rgba(0, 0, 0, 0.1);
  color: white;
  box-shadow: 0 0 10px 4px black;
  text-shadow: 3px 3px black;
  cursor: pointer;
}

option {
  text-align: center;
  text-transform: capitalize;
  font-size: 1.2rem;
  background-color: rgba(255, 255, 255);
  color: rgb(0, 0, 0);
}
</style>