<template>
  <div class="room">
    <room-measurements class="room-measurements" />
    <room-image class="room-image" :roomImageUrl="roomImageUrl" />
    <room-selectors @selected="changeImage" class="room-selectors" />
  </div>
</template>

<script>
import RoomImage from "./RoomImage.vue";
import RoomSelectors from "./RoomSelectors.vue";
import RoomMeasurements from "./RoomMeasurements.vue";

export default {
  components: { RoomImage, RoomSelectors, RoomMeasurements },
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
  top: 51%;
  left: 50%;
  transform: translateX(-50%) translateY(-50%);
  width: 40rem;
  max-width: 82vw;
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

.room-measurements {
  position: absolute;
  top: 27%;
  left: 50%;
  width: 35rem;
  max-width: 80vw;
  transform: translateX(-50%) translateY(-50%);
  height: 5rem;
}

@media only screen and (max-width: 525px) {
  .room-measurements {
    height: 8rem;
  }
}

@media only screen and (max-width: 400px) {
  .room-measurements {
    max-width: 90vw;
  }
}

@media only screen and (max-height: 652px) {
  .room-image {
    top: 56%;
    width: 15rem;
  }

  .room-measurements {
    top: 20%;
  }

  .room-selectors {
    display: none;
  }
}
</style>