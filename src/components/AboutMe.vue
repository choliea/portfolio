<template>
    <section>
        <header class="title">About me</header>
        <div class="aboutme">
            <div class="profile">
                <img class="profImg" src="../assets/mypic.jpg" alt="">
            </div>
            <div class="profText">
                <ul>
                    <li>
                        <div class="icon">
                        <font-awesome-icon :icon="['fas', 'person']" />
                        </div>
                        <span>최유강</span>
                    </li>
                    <li>
                        <div class="icon">
                        <font-awesome-icon :icon="['fas', 'cake-candles']" />
                        </div>
                        <span>1997.09.01.</span>
                    </li>
                    <li>
                        <div class="icon">
                        <font-awesome-icon :icon="['fas', 'location-dot']" />
                        </div>
                        <span>관악구 신림동</span>
                    </li>
                    <li>
                        <div class="icon">
                        <font-awesome-icon :icon="['fas', 'envelope']" />
                        </div>
                        <span>choiyg3234@gmail.com</span>
                    </li>
                    <li>
                        <div class="icon">
                        <font-awesome-icon :icon="['fas', 'graduation-cap']" />
                        </div>
                        <span>목포해양대학교 항해학부</span>
                    </li>
                    <li>
                        <div class="icon">
                        <font-awesome-icon :icon="['fas', 'code']" />
                        </div>
                        <span>2023.05.~2023.11. ITWILL 자바 백엔드 과정 수료</span>
                    </li>
                    <li>
                        <div class="icon">
                        <font-awesome-icon :icon="['fas', 'certificate']" />
                        </div>
                        <span>2023.06.09. 정보처리기사 취득</span>
                    </li>
                    <li>
                        <div class="icon">
                        <font-awesome-icon :icon="['fas', 'clipboard']" />
                        </div>
                        <a href="https://youarethebestcoding.tistory.com/" target="_blank">
                            <span>Blog</span>
                        </a>&nbsp;
                        <div class="icon">
                        <font-awesome-icon :icon="['fab', 'github']" />
                        </div>
                        <a href="https://github.com/choliea" target="_blank">
                            <span>GitHub</span>
                        </a>                   
                    </li>
                </ul>
            </div>
        </div>
    </section>
</template>

<script>

    export default {
        name: 'AboutMe',
        
        
    }
</script>

<style scoped>

.aboutme {
    display: flex;
    padding: 10px;
    align-items: center;
    padding-left: 10%;
}
.profText,
.profile {
    display: inline-block;
    vertical-align: bottom;
}
.profText {
    padding-left: 3%;
}
.profile {
    width: 310px;
    height: 420px; 
    border-radius: 70%;
    overflow: hidden;
    background: #BDBDBD;
    
}
.profImg {
    width: 100%;
    height: 100%;
    object-fit: cover;
}

.icon {
    display: inline-block; /* 인라인 블록 요소로 설정 */
    width: 50px; 
    height: 50px; 
  }

  .icon font-awesome-icon {
    vertical-align: middle; /* 아이콘을 세로 중앙 정렬 */
  }

  .icon span {
    vertical-align: middle; /* 텍스트를 세로 중앙 정렬 */
  }

</style>