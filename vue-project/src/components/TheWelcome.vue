<script setup>
const props = defineProps(['floor'])
</script>

<template>
  <div class="floor">
    <button class="btn-floor">o</button>
    <span>| {{ props.floor }}</span>
  </div>
</template>

<style>
.floor {
  display: flex;
  height: 100px;
  width: 100%;
  border-top: 1px solid #000;
  border-left: 1px solid #000;
  align-items: center;
  gap: 15px;
}

.btn-floor {
  width: 50px;
  padding: 10px 30px;
  margin-left: 15px;
  cursor: pointer;
}
</style>
