<script setup>
import { ref } from "vue";

const showModal = ref(false);
</script>

<template>
  <main>
    <div v-if="showModal" class="overlay">
      <div class="modal">
        <textarea name="note" id="note" cols="30" rows="10"></textarea>
        <button>Add Note</button>
        <button class="close">Close</button>
      </div>
    </div>
    <div class="container">
      <header>
        <h1>Notes {{showModal}}</h1>
        <button @click="showModal = true">+</button>
      </header>
      <div class="cards-container">
        <div class="card">
          <p class="main-text">
            Lorem, ipsum dolor sit amet consectetur adipisicing elit. Rerum quos
            voluptatibus vitae pariatur fuga, nemo recusandae.
          </p>
          <p class="date">04/07/2025</p>
        </div>
      </div>
    </div>
  </main>
</template>

<style scoped>
main {
  height: 100vh;
  width: 100vw;
}
.overlay {
  position: absolute;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.23);
  z-index: 5;
  display: flex;
  align-items: center;
  justify-content: center;
}

.container {
  max-width: 1000px;
  padding: 10px;
  margin: 0 auto;
}
header {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
h1 {
  font-weight: bold;
  margin-bottom: 25px;
  font-size: 75px;
}
header button {
  border: none;
  height: 50px;
  width: 50px;
  padding: 10px;
  background-color: rgb(25, 176, 176);
  cursor: pointer;
  border-radius: 100%;
  font-size: 20px;
  color: black;
}

.cards-container {
  display: flex;
  flex-wrap: wrap;
}
.card {
  width: 225px;
  height: 225px;
  background: rgb(237, 182, 44);
  padding: 10px;
  border-radius: 15px;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  margin-right: 20px;
  margin-bottom: 20px;
}
.main-text {
  color: black;
}
.date {
  font-size: 12.5px;
  font-weight: bold;
  color: black;
}
.modal {
  width: 750px;
  background-color: white;
  border-radius: 10px;
  padding: 30px;
  position: relative;
  display: flex;
  flex-direction: column;
}
.modal button {
  padding: 10px 20px;
  font-size: 20px;
  width: 100%;
  background-color: blueviolet;
  color: white;
  margin-top: 15px;
  cursor: pointer;
}
.modal .close {
  background-color: rgb(193, 15, 15);
  margin-top: 7px;
}
</style>
