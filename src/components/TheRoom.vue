<template>
  <div class="room">
    <room-image class="room-image" :roomImageUrl="roomImageUrl" />
    <room-selectors @selected="changeImage" class="room-selectors" />
  </div>
</template>

<script>
import RoomImage from "./RoomImage.vue";
import RoomSelectors from "./RoomSelectors.vue";

export default {
  components: { RoomImage, RoomSelectors },
  data() {
    return {
      roomImageUrl: "base_room",
    };
  },
  methods: {
    changeImage(criteria, type) {
      if (criteria && type) {
        this.roomImageUrl = `room_${this.formated(criteria)}_${this.formated(
          type
        )}`;
      } else {
        this.roomImageUrl = "base_room";
      }
    },
    formated(str) {
      return str.toLowerCase().split(" ").join("_");
    },
  },
};
</script>

<style scoped>
.room-image {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translateX(-50%) translateY(-50%);
  width: 40rem;
  max-width: 85vw;
  overflow: hidden;
  border-radius: 30px;
  box-shadow: 0 0 40px 5px black;
  transition: all 0.3s ease-in-out;
}

.room-image:hover {
  width: 39.5rem;
}

.room-selectors {
  position: absolute;
  top: 77%;
  left: 50%;
  transform: translateX(-50%) translateY(-50%);
  display: flex;
  flex-direction: column;
  width: 10rem;
  align-items: center;
  justify-content: space-evenly;
  height: 8rem;
}
</style>