<template>
  <!-- <div class="right-nav"></div> -->
  <div class="right-body">
    <img src="/assets/nuxtxhat-logo2-wobg.png" />
    <h1>Download NuxtChat for Windows</h1>
    <p>
      Make calls, share your screen and get a faster experience when you
      download the Windows app.
    </p>
    <button>Get from Microsoft Store</button>
    <p>
      <i class="fa-solid fa-lock"></i> Your personal messages are end-to-end
      encrypted.
    </p>
  </div>
  <!-- <div class="right-chat"></div> -->
</template>

<style scoped>
.right-nav {
  display: flex;
  justify-content: space-between;
  width: 100%;
  height: 80px;
  background-color: #024950;
}
.right-body {
  width: 100%;
  height: 742px;
  background-color: #024950;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  font-family: "Mukta", sans-serif;
  color: #afdde5;
}

.right-body > img {
  width: 36%;
  height: 42%;
  margin-top: 90px;
}

.right-body > h1 {
  font-size: 3rem;
  margin: 0px;
  font-weight: 300;
}

.right-body > p {
  font-size: 1rem;
  width: 60%;
  text-align: center;
  margin-bottom: 10px;
}

.right-body > p:last-child {
  font-size: 0.9rem;
}

.right-body > button {
  width: 20%;
  font-size: 1rem;
  height: 50px;
  border-radius: 20px;
  font-family: "Mukta", sans-serif;
  background-color: #111b21;
  color: #afdde5;
  border: 0px;
  cursor: pointer;
  margin-bottom: 60px;
}

.right-chat {
  width: 100%;
  height: 60px;
  background-color: #024950;
}
</style>
