<template>
  <div class="container">
    <div class="measurements">
      <label for="width">Floor Width <span>(cm)</span>:</label>
      <input type="number" id="width" />
    </div>
    <div class="measurements">
      <label for="length">Floor Length <span>(cm)</span>:</label>
      <input type="number" id="length" />
    </div>
    <div class="measurements">
      <label for="height">Room Height <span>(cm)</span>:</label>
      <input type="number" id="height" />
    </div>
  </div>
</template>

<style scoped>
.container {
  display: flex;
  align-items: center;
  justify-content: space-evenly;
}

.measurements {
  max-width: 30%;
  display: flex;
  justify-content: space-evenly;
}

.measurements label {
  color: white;
  text-shadow: 2px 2px black;
  font-size: 1rem;
}

span {
  font-size: 0.8rem;
}

.measurements input {
  width: 20%;
  font-weight: 600;
  text-align: center;
}

@media only screen and (max-width: 662px) {
  .container {
    flex-direction: column;
  }

  .measurements {
    min-width: 50%;
    justify-content: space-between;
  }
}

@media only screen and (max-width: 400px) {
  .measurements {
    min-width: 70%;
  }
}
</style>