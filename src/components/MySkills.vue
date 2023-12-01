<template>
  <div class="skill">
    <header class="title">Skills</header>
    <main>
      <section>
        <div class="category">Backend</div>
        <ul class="tech-list">
          <li class="tech-item">Java</li>
          <li class="tech-item">Spring Boot</li>
          <li class="tech-item">JPA</li>
          <li class="tech-item">MyBatis</li>
          <li class="tech-item">MySQL</li>
          <li class="tech-item">Oracle</li>
          <li class="tech-item">JSP</li>
        </ul>
      </section>

      <section>
        <div class="category">Frontend</div>
        <ul class="tech-list">
          <li class="tech-item">JavaScript</li>
          <li class="tech-item">Vue.js</li>
          <li class="tech-item">jQuery</li>
          <li class="tech-item">HTML</li>
          <li class="tech-item">CSS</li>
          <li class="tech-item">Bootstrap</li>
        </ul>
      </section>

      <section>
        <div class="category">Server</div>
        <ul class="tech-list">
          <li class="tech-item">AWS</li>
          <li class="tech-item">ApacheTomcat</li>
        </ul>
      </section>

      <section>
        <div class="category">Template Engines</div>
        <ul class="tech-list">
          <li class="tech-item">Thymeleaf</li>
          <li class="tech-item">Handlebars</li>
        </ul>
      </section>

      <section>
        <div class="category">Others</div>
        <ul class="tech-list">
          <li class="tech-item">GitHub</li>
        </ul>
      </section>
    </main>
  </div>
</template>

<script>
export default {};
</script>

<style scoped>


main {
  display: flex;
  justify-content: space-between;
  flex-wrap: wrap;
}
.skill>.title{
  color: #D6FFF6;
}
section {
  width: 15%;
  height: 400px;
  margin: 20px;
  margin-bottom: 55px;
  border-radius: 20px;
  align-items: center;
  text-align: center;
  vertical-align: center;
  background-color: #D6FFF6;
  color: #00b890;
}
.category {
  font-size: 2em;
  font-weight: 600;
  margin-bottom: 0.5em;
  margin-top: 1em;
}

.tech-list {
  list-style-type: none;
  padding: 0;
  padding-bottom: 50%;
}

.tech-item {
  margin-bottom: 0.5em;
}
    @media (max-width: 768px) {
      section {
        width: 100%; /* Full width for smaller screens */
      }
    }
</style>
