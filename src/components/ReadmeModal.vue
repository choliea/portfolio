<template>
  <div class="black-bg">
    <div class="white-bg">
        <p @click="$emit('close',false)">X</p>
      <iframe :src="url" ></iframe>
    </div>
  </div>
</template>

<script>
export default {
  
    props:['url']
};
</script>

<style scoped>
p{
  text-align: right;
  font-size: xx-large;
  font-weight: 300;
  color: black;
}

.black-bg {
  box-sizing: border-box;
  width: 100%; height: 100%;
  background: rgba(0,0,0,0.5);
  position: fixed; 
  padding: 20px;
  z-index: 1000;
}
.white-bg {
  box-sizing: border-box;
  width: 100%; height: 100%;
  background: white;
  border-radius: 8px;
  padding: 20px;
}
iframe{
  width: 100%;
  height: 100%;
}
</style>
