<script setup>
import { ref } from 'vue'
import TheWelcome from './components/TheWelcome.vue'

const elevatorFloor = ref(1)
const elevatorIsBusy = ref(false)
const elevatorWait = ref(false)
const elevatorDefault = ref(true)

function clickOnBtnFloor(e) {

  if (elevatorDefault.value === true) {

    elevatorIsBusy.value = true

    setTimeout(() => {
      elevatorIsBusy.value = false
      elevatorWait.value = true
      setTimeout(() => {
        elevatorWait.value = false
      }, 3000)
    }, 2000)






    if (elevatorFloor.value == e.target.id) {
      return
    }




    elevatorFloor.value = `floor` + e.target.id
  }




}
</script>

<template>

  <main>
    <div class="flex">
      <div class="elevator" :class=elevatorFloor>
        <div class="lamp" :class="{ busy: elevatorIsBusy, wait: elevatorWait }"></div>
      </div>
      <div class='floors'>
        <div v-for="  floor   in   5  ">
          <TheWelcome :floor=floor :clickOnBtnFloor=clickOnBtnFloor />
        </div>

      </div>
    </div>


  </main>
</template>

<style>
.floors {
  width: 90%;
}

.lamp {
  width: 25px;
  height: 25px;
  border-radius: 50%;
  background: #24df4c;
  animation: blinker 1s linear infinite;
}

.lamp.busy {
  background: #750101;
  animation: none
}

.lamp.wait {
  background: #dbaa07;
  animation: blinker 1s linear infinite;
}


@keyframes blinker {
  50% {
    opacity: 0;
  }
}

.elevator {
  display: block;
  height: 100px;
  width: 200px;
  background: #4e51ff;
  position: absolute;
  left: 0;
  bottom: 0px;
  transition: ease-out 2s;
}

.elevator.floor4 {
  bottom: 300px;
}

.elevator.floor1 {
  bottom: 0px;
}

.elevator.floor2 {
  bottom: 100px;
}

.elevator.floor3 {
  bottom: 200px;
}

.elevator.floor5 {
  bottom: 400px;
}

.flex {

  display: flex;
  margin-left: 200px;
}

.floors {
  display: flex;
  flex-direction: column-reverse;
  position: absolute;
  bottom: 0;
}
</style>