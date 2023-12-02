<template>
  <ReadmeModal
    v-if="popstate"
    :popState="popstate"
    @close="changeState"
    :url="this.modalUrl"
  ></ReadmeModal>
  <div id="home">
  <AppBar
    @scrollToContent="scrollToContent"
    :style="{ backgroundColor: appbarBackgroundColor, color: appbarTextColor }"></AppBar>
    <div id="hometext">
      <header>최유강's Web Developer Portfolio</header>
      <p id="homep">
        안녕하세요, 최유강입니다. <br />
        저는 백엔드에 집중하고 있지만,<br />
        프론트와 백엔드 관계없이 다양한 기술을 배우는 것을 좋아하는 웹
        개발자입니다. <br />
        제가 만든 애플리케이션이 사용자와 개발자 모두에게 인정받고, <br />
        서비스와 회사가 함께 성장하는 것이 제 꿈입니다. <br />
      </p>
    </div>
  </div>
  <div class="main-content">
    <div class="contents" id="aboutme">
      <AboutMe></AboutMe>
    </div>
    <div class="contents" id="skill">
      <MySkills></MySkills>
    </div>
    <div class="contents" id="project">
      <header class="title">Projects</header>
      <div class="row">
      <MyPortfolios
        id="danaga"
        class="project"
        :portfolio="portfolio1"
        @openReadme="changeState"
      ></MyPortfolios>
      <MyPortfolios
        id="sellphone"
        class="project"
        :portfolio="portfolio2"
        @openReadme="changeState"
      ></MyPortfolios>
      <MyPortfolios
        id="portfolio"
        class="project"
        :portfolio="portfolio3"
        @openReadme="changeState"
      ></MyPortfolios>
      <MyPortfolios
        id="goryeo"
        class="project"
        :portfolio="portfolio4"
        @openReadme="changeState"
      ></MyPortfolios>
      </div>
    </div>
  </div>
</template>

<script>
import ReadmeModal from "./components/ReadmeModal.vue";
import AboutMe from "./components/AboutMe.vue";
import MySkills from "./components/MySkills.vue";
import MyPortfolios from "./components/MyPortfolios.vue";
import AppBar from "./components/AppBar.vue";
import sellphoneReadme from './assets/sellphoneReadme.pdf';
import goryeo from './assets/goryeo.pdf';
import eleven from './assets/eleven.png'

export default {
  data() {
    return {
      appbarBackgroundColor: "transparent", // 초기에 투명하게 설정
      appbarTextColor: "beige",
      modalUrl: '',

      popstate: false,
      portfolio1: {
        title: "Danaga",
        day: "2023.10.~ 2023.11. (1개월) By Team.Avengers",
        projectImgUrl: "danaga.png",
        description: `
          <p>전자제품 판매 사이트 다나와를 레퍼런스한 웹 사이트입니다.<br>
          아이티윌 자바 백엔드 과정의 마지막 프로젝트로 실무에서 가장 많이 요구되어지는 형태인 쇼핑몰을 선택했고, <br>
          그중에서도 다른 일반 상품과 달리 데이터를 다루는데 조금 더 많은 고민이 필요하다고 생각되는 전자제품을 선택하게 되었습니다. <br>
          저는 Product 파트를 맡았고, 제품 검색 기능, 최근 본 상품, 관심상품 서비스를 구현하였습니다. </p>
          
          <p>DataJPA를 처음으로 적용해보면서 많은 시행착오를 겪었지만, 책과 공식API 문서를 찾아가며 더 많이 배울 수 있었고, <br>
          Thymeleaf와 Handlerbars를 사용하면서 SSR과 CSR을 제대로 이해할 수 있었습니다. </p>

          <p>또한, 배포를 경험해보기 위해 AWS서비스들의 개념을 공부하고 elasticbeanstalk을 이용해 배포 후<br>
             Github actions를 이용한 무중단 배포까지 성공적으로 마치는 좋은 경험이 되었습니다.</p>
          `,
        readmeUrl: "https://youarethebestcoding.tistory.com/126",
        repositoryUrl: "https://github.com/choliea/danaga/",
      },
      portfolio2: {
        title: "SellPhone",
        day: "2023.08.18. ~ 2023.08.25. (1주일) By Team.",
        projectImgUrl: "sellphone.png",
        description: `
        <p>휴대폰 판매 사이트 첫 웹 사이트 프로젝트입니다.<br>
          휴대폰과 요금제를 선택하면 할인 정보를 확인하고 비교할 수 있습니다 <br>
          저는 Order 파트를 맡아 주문폼부터 주문완료까지 주문 서비스와 주문내역 디테일 페이지를 구현하였습니다.<br>
          JSP, MyBatis 기술을 이용해 백엔드를 구현하였고, 처음으로 javascript를 활용해 프론트엔드를 구현했습니다.<br>
          주문폼에서는 선택된 요금제와 약정기간에 따라 할인 요금과 월 납부금이 계산되어 표시되고, <br>
          주문정보를 입력하고 팝업창을 통해 가상의 계좌 또는 신용카드 정보를 확인하여 <br>
          정보가 일치하면 결제가 완료되게 구현하였습니다.<br> 
          주문내역 디테일 페이지에서는 주문정보를 표시하고, 그림으로 배송상태를 직관적으로 알 수 있게 하였습니다. <br>
          </p>
        `,
        readmeUrl: sellphoneReadme,
        repositoryUrl: "https://github.com/choliea/2nd-Project---SellPhone-",
      },
      portfolio3: {
        title: "portfolio",
        day: "2023.12.01. ~2023.12.02.",
        projectImgUrl: "portfolio.png",
        description: `
        포트폴리오를 위해 만든 정적 웹사이트입니다. <br>
        기본적인 Vue.js를 학습하고, 배운내용을 복습 및 활용해보기 위해 제작해보았습니다.<br>
        추가로 netlify를 통해 배포까지 진행하였습니다.
        `,
        readmeUrl: eleven ,
        repositoryUrl: "https://github.com/choliea/portfolio",
      },
      portfolio4: {
        title: "Goguryeo Hotel",
        day:"2023.07.14. ~ 2023.07.25. (12일) By Team.오졌죠",
        projectImgUrl: 'goryeo.png',
        description: `
          <p>
            고객이 원하는 체크인, 체크아웃 날짜를 입력받아 해당 기간 비어있는 방을 조회하고 예약할 수 있는 호텔 예약 서비스입니다.<br>
            Java와 SQL, JDBC를 배우고 난뒤 지금은 거의 사용하지 않는 Swing GUI로 구현한 간단한 애플리케이션입니다. <br>
            서버가 DB와 데이터를 주고 받고 받은 데이터를 가공하는 과정을 직접 실습해 볼 수 있었던 프로젝트였습니다.<br>
            저는 빈 방을 검색하고 선택한 방을 (가)예약한 후 예약한 내역을 확인할 수 있는 고객 페이지와 <br>
            관리자가 예약 내역을 검색하고 수정할 수 있는 관리자 예약 페이지를 구현하였습니다.
            </p>
        `,
        readmeUrl: goryeo,
        repositoryUrl: 'https://github.com/choliea/1st-Project-GoryeoHotel',
      }
    };
  },
  methods: {
    changeState(url) {
      this.modalUrl = url;
      this.popstate = !this.popstate;
    },
    scrollToContent(section) {
      const element = document.getElementById(section);
      if (element) {
        element.scrollIntoView({ behavior: "smooth" });
      }
    },
    handleScroll() {
      // 스크롤 위치에 따라 배경색 변경
      this.appbarBackgroundColor =
        window.scrollY > 50 ? "white" : "transparent";
      this.appbarTextColor = window.scrollY > 50 ? "black" : "beige";
    },
   
  },
  mounted() {
    window.addEventListener("scroll", this.handleScroll);
  },
  beforeUnmount() {
    window.removeEventListener("scroll", this.handleScroll);
  },
  components: {
    AboutMe: AboutMe,
    MySkills: MySkills,
    MyPortfolios: MyPortfolios,
    ReadmeModal: ReadmeModal,
    AppBar: AppBar,
  },
};
</script>

<style>
@import "assets/css/fonts.css";

@media only screen and (max-width: 600px) {
      #hometext > #homep {
        font-size: 13px;
      }
      #hometext header {
        margin-top :50px;
      }
    }
body {
  margin: 0;
  font-family: "baemin";
  color: beige;
}
.title {
  text-align: center;
  font-size: 3em;
  font-family: "baemin";
  padding: 30px;
  align-items: center;
}
.row{
  display: flex;
  justify-content: space-evenly;
  flex-wrap: wrap;
  box-sizing: border-box;
}
.project > .title {
  font-family: Roobert, -apple-system, BlinkMacSystemFont, "Segoe UI", Helvetica,
    Arial, sans-serif, "Apple Color Emoji", "Segoe UI Emoji", "Segoe UI Symbol";
  font-weight: 900;
}
ul {
  font-size: 25px;
  list-style-type: none;
  font-family: "baemin";
}
.contents {
  margin-bottom: 60px;

  /* background-image: url('assets/contentsbg.jpg'); */
  color: black;
}
#home {
  background-image: url("assets/bg.jpg");
  background-size: cover;
  height: 1000px;
  width: 100%;
}
#homep {
  line-height: 2.5;
  margin-top: 5%;
}
#hometext {
  text-align: center;
  padding: 15%;
}
#hometext header {
  font-size: 4em;
}
#hometext p {
  font-size: 1.5em;
  font-family: Verdana, Geneva, Tahoma, sans-serif;
}
.main-content {
  padding-top: 60px;
}
#skill {
  background-color: #00b890;
  color: beige;
}

.project {
  transition: width 0.3s ease-in-out, height 0.3s ease-in-out;
  /* margin-left: 10%; */
  /* margin-right: 10%; */
  border-radius: 20px;
  width: 45%;
  height: 40%;
  margin: 10px;
   background-color: rgb(255, 234, 0);

}

.project:hover {
  width: 45%;
  height: 100%;
}
.project:hover .description {
  font-size: x-large;
}
</style>
