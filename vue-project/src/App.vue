<script setup>
import TheWelcome from './components/TheWelcome.vue'
import Elevator from './components/elevator.vue'
</script>

<template>

  <main>
    <div class="flex">
      <Elevator />
      <div class='floors'>
        <div v-for="floor in 5">
          <TheWelcome :floor=floor />
        </div>

      </div>
    </div>


  </main>
</template>

<style>
.floors {
  width: 90%;
}

.flex {

  display: flex;
  margin-left: 200px;
}

.floors {
  position: absolute;
  bottom: 0;
}
</style>