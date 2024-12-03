<template>
  <div>
    <div class="middle-bar">
      <div class="search-bar">
        <span class="search-icon">
          <i class="fa-solid fa-magnifying-glass"></i>
        </span>
        <input
          type="text"
          v-model="searchVal"
          placeholder="Search or start new chat"
        />
      </div>
      <div class="btn-div">
        <button @click="setFilter('all')">All</button>
        <button @click="setFilter('unread')">Unread</button>
        <button @click="setFilter('groups')">Groups</button>
      </div>
    </div>

    <div class="chat-container">
      <Message
        v-for="(msg, index) in finalMessages"
        :key="index"
        :name="msg.name"
        :message="msg.message"
        :time="msg.time"
        :read="msg.read"
        :type="msg.type"
        :img="msg.img"
        @updateRead="updateRead(index)"
      />
    </div>
  </div>
</template>

<script setup>
import { ref, computed, watch } from "vue";
import Message from "@/components/Message.vue";
import { messages as dataMessages } from "@/data/messages";

const messages = ref(dataMessages);
const filter = ref("all");
const searchVal = ref("");

// watch(searchVal, (newVal) => {
// console.log(newVal);
// });

const setFilter = (newFilter) => {
  console.log(newFilter);
  filter.value = newFilter;
};

const finalMessages = computed(() => {
  let filteredMessages = messages.value;

  if (filter.value === "unread") {
    filteredMessages = filteredMessages.filter((msg) => !msg.read);
  } else if (filter.value === "groups") {
    filteredMessages = filteredMessages.filter((msg) => msg.type === "group");
  }

  if (searchVal.value) {
    const searchValue = searchVal.value.toLowerCase();
    filteredMessages = filteredMessages.filter((msg) =>
      msg.name.toLowerCase().includes(searchValue)
    );
  }

  return filteredMessages;
});

const updateRead = (index) => {
  console.log(finalMessages.value[index].read);
  finalMessages.value[index].read = true;
  console.log(finalMessages.value[index].read);
};
</script>

<style scoped>
.middle-bar {
  width: 100%;
  height: 110px;
  background-color: #111b21;
  display: flex;
  justify-content: center;
  padding: 0px 11px;
  flex-direction: column;
  font-family: "Mukta", sans-serif;
  border-bottom: 1px solid #024950;
}

.search-bar {
  width: 90%;
  height: 30%;
  display: flex;
  align-items: center;
  margin-top: 10px;
  padding: 5px 10px;
  border-radius: 10px;
  background-color: #024950;
  font-family: "Mukta", sans-serif;
}

.search-icon {
  font-size: 20px;
  margin-right: 10px;
  color: #888;
}

input {
  border: none;
  outline: none;
  background: transparent;
  flex: 1;
  font-size: 16px;
  color: #afdde5;
}
input::placeholder {
  color: #afdde5;
}

.btn-div {
  width: 100%;
  height: 50px;
}

button {
  padding: 0px 7px;
  height: 70%;
  border-radius: 10px;
  cursor: pointer;
  margin: 10px 10px 5px;
  font-size: 1rem;
  font-family: "Mukta", sans-serif;
  background-color: #024950;
  color: #afdde5;
  border: 0px;
}

.chat-container {
  width: 100%;
  height: 548px;
  margin: 0 auto;
  background-color: #024950;
  overflow-y: scroll;
  -ms-overflow-style: none; /* IE and Edge */
  scrollbar-width: none;
}
i {
  color: #afdde5;
  font-size: 1rem;
}
</style>
