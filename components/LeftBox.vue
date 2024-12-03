<template>
  <div class="left-nav">
    <img src="/assets/pfp.png" />
    <div class="icons-div">
      <i class="fa-solid fa-user-group"></i>
      <i class="fa-solid fa-comment-dots"></i>
      <i class="fa-solid fa-campground"></i>
      <i class="fa-solid fa-ellipsis-vertical"></i>
    </div>
  </div>
  <!-- <LeftMiddleBar /> -->
  <MessageBox />
</template>
<style scoped>
.left-nav {
  display: flex;
  justify-content: space-between;
  width: 100%;
  height: 80px;
  background-color: #024950;
  /* border-right: 2px solid #afdde5; */
}
img {
  width: 10%;
  height: 70%;
  border-radius: 30px;
  margin: 9px 30px 0px;
}
i {
  font-size: 1.4rem;
  cursor: pointer;
  color: #afdde5;
}
.icons-div {
  display: flex;
  justify-content: space-around;
  width: 50%;
  padding: 28px 5px;
}
</style>
