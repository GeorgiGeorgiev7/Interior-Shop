<template>
  <div>
    <img
      ref="image"
      class="image"
      :src="require(`../assets/${roomImageUrl}.jpg`)"
      alt="base_room.jpg"
    />
  </div>
</template>

<script>
export default {
  props: {
    roomImageUrl: {
      type: String,
      required: true,
    },
  },
};
</script>

<style scoped>
.image {
  width: 100%;
  height: auto;
  border-radius: 30px;
}
</style>