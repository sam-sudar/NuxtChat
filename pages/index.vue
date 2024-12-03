<template>
  <!-- <MessageBox /> -->
  <div class="main">
    <div class="left">
      <LeftBox />
    </div>
    <div class="right">
      <RightBox />
    </div>
  </div>
</template>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box; /* Ensures consistent sizing across browsers */
}

html,
body {
  height: 100%;
  width: 100%;
  background-color: #024950;
}

.main {
  background-color: blueviolet;
  width: 100%;
  height: 100vh; /* Adjusts height based on viewport */
  display: flex;
}

.left,
.right {
  height: 100%;
}

.left {
  width: 35%; /* Use percentage to adapt to different browser sizes */
  background-color: #024950;
}

.right {
  width: 65%; /* Use percentage to adapt to different browser sizes */
  background-color: #111b21;
}
</style>
