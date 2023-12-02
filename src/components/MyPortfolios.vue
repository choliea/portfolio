<template>
    <div class="portfolio-content" ref="portfolioContent" @click="handleClick">
        <header class="title">{{ portfolio.title }}</header>
        <span>{{ portfolio.day }}</span><br>
        <img :src="require(`../assets/${portfolio.projectImgUrl}`)" alt=""><br>
        <div class="description" v-html="portfolio.description"></div>
        <button @click="openRepository">소스코드</button>&nbsp;
        <button @click="this.$emit('openReadme',this.portfolio.readmeUrl)">자세히보기</button><br>
        
        <br>
    </div>
</template>

<script>

    export default {
        data() {
            return {
            
               
            }
        },
        props:[
            'portfolio',
        ],
        methods:{
            openRepository(){
                window.open(this.portfolio.repositoryUrl,"_blank");
            },
           handleClick() {
      this.$emit('click', this);
    },
        },
        // components:{
        //     'ReadmeModal':ReadmeModal,
        // }
    }
</script>

<style scoped>

div.portfolio-content{
    text-align: center;
    box-sizing: border-box;
}

span{
    font-weight: 600;
    font-size: 23px;
    font-family: Roobert,-apple-system,BlinkMacSystemFont,"Segoe UI",Helvetica,Arial,sans-serif,"Apple Color Emoji","Segoe UI Emoji","Segoe UI Symbol";
}
div.description{
    /* font-weight: 300; */
    font-size: large;
    width: 90%;
    text-align: left;
    /* align-items: center; */
    margin-left: 5%;
    /* font-family: Roobert,-apple-system,BlinkMacSystemFont,"Segoe UI",Helvetica,Arial,sans-serif,"Apple Color Emoji","Segoe UI Emoji","Segoe UI Symbol"; */
     /* max-height: 500px; 원하는 최대 높이로 설정 */
    line-height: 1.5;
}


img{
    width: 90%;
    height: 70%;
    max-height: 300px;
    overflow: hidden;
    padding: 1em;
}

/* CSS */
button {
  appearance: none;
  background-color: #000000;
  border: 2px solid #1A1A1A;
  border-radius: 15px;
  box-sizing: border-box;
  color: #FFFFFF;
  cursor: pointer;
  display: inline-block;
  font-family: Roobert,-apple-system,BlinkMacSystemFont,"Segoe UI",Helvetica,Arial,sans-serif,"Apple Color Emoji","Segoe UI Emoji","Segoe UI Symbol";
  font-size: 16px;
  font-weight: 600;
  line-height: normal;
  margin: 0;
  min-height: 40px;
  min-width: 0;
  outline: none;
  padding: 16px 24px;
  text-align: center;
  text-decoration: none;
  transition: all 300ms cubic-bezier(.23, 1, 0.32, 1);
  user-select: none;
  -webkit-user-select: none;
  touch-action: manipulation;
  width: 45%;
  will-change: transform;
}

button:disabled {
  pointer-events: none;
}

button:hover {
  box-shadow: rgba(0, 0, 0, 0.25) 0 8px 15px;
  transform: translateY(-2px);
}

button:active {
  box-shadow: none;
  transform: translateY(0);
}
</style>