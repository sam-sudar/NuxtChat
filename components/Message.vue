<template>
  <div class="message" @click="changeRead">
    <div class="img-div">
      <img :src="imgSrc" alt="User Image" />
    </div>
    <div class="content-div">
      <div class="message-header">
        <strong>{{ name }}</strong>
        <span class="time">{{ time }}</span>
      </div>
      <div class="message-body">
        <p>{{ message }}</p>
        <span class="status" v-show="!read">🟢</span>
      </div>
    </div>
  </div>
</template>

<script setup>
import { computed } from "vue";

const props = defineProps({
  name: String,
  message: String,
  time: String,
  read: Boolean,
  type: String,
  img: String,
});

const imgSrc = computed(() => `/assets/${props.img}.png`);

const emit = defineEmits(["updateRead"]);

const changeRead = () => {
  emit("updateRead");
};
</script>

<style scoped>
.message {
  height: 110px;
  padding: 10px;
  background-color: #111b21;
  font-family: "Mukta", sans-serif;
  color: #afdde5;
  cursor: pointer;
  display: flex;
}

.img-div {
  width: 17%;
  height: 100%;
}

img {
  width: 70%;
  height: 70%;
  border-radius: 50px;
  margin: 9px 11px 0px;
}

.content-div {
  width: 83%;
  height: 100%;
  padding-left: 10px;
  border-bottom: 1px solid #024950;
}

.message-header {
  display: flex;
  justify-content: space-between;
  font-weight: bold;
  font-size: 1.2rem;
}

.message-body {
  height: 60%;
  display: flex;
  justify-content: space-between;
}

.message-body p {
  margin: 2px 0px;
  height: 35px;
}

.time {
  font-size: 0.8em;
  color: gray;
}
.status {
  padding-top: 3px;
}
</style>
