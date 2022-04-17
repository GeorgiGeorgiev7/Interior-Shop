<template>
  <h1>Interior</h1>
</template>

<style scoped>
h1 {
  position: absolute;
  top: 2rem;
  left: 50%;
  color: white;
  font-size: 8rem;
  text-shadow: 7px 5px black;
  transform: translateX(-50%) translateY(-50%);
  max-width: 100%;
  overflow: hidden;
}

@media only screen and (max-width: 525px) {
  h1 {
    font-size: 6rem;
  }
}

@media only screen and (max-width: 400px) {
  h1 {
    font-size: 5rem;
  }
}

@media only screen and (max-width: 300px) {
  h1 {
    font-size: 4rem;
  }
}

@media only screen and (max-width: 250px) {
  h1 {
    font-size: 3rem;
  }
}
</style>