<template>
  <div class="app-bar">
    <div class="app-title">최유강's portfolio</div>
    <div class="app-menu">
      <span class="app-menu-item" @click="scrollToContent('home')">Home</span>
        <span class="app-menu-item" @click="scrollToContent('aboutme')">About me</span>
      <span class="app-menu-item" @click="scrollToContent('skill')">Skills</span>
      <span class="app-menu-item" @click="scrollToContent('project')">Projects</span>
    </div>
  </div>
</template>

<script>
export default {
    methods:{
        scrollToContent(section){
            this.$emit('scrollToContent',section);
        }
    }
};
</script>

<style scoped>
.app-bar {
  padding: 10px;
  /* color: white; */
  display: flex;
  justify-content: space-between;
  align-items: center;
  position: fixed;
  top: 0;
  width: 100%;
  z-index: 1000;
  transition: background-color 0.3s;
}

.app-title {
  font-size: 2.5rem;
  margin: 0;
}

.app-menu {
  display: flex;
  gap: 30px;
  padding-right: 30px;
}

.app-menu-item {
  /* color: white; */
  text-decoration: none;
  font-size: 1.5em;
}
@media only screen and (max-width: 600px) {
    .app-title {
  font-size: 1rem;
  
}


.app-menu-item {
  /* color: white; */
  
  font-size: 0.5em;
}
    }

</style>
