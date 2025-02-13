<template>
  <div>
    <section id="navbar" style="font-family: 'Andalé Mono', monospace;">
      <nav class="navbar fixed-top navbar-expand-lg navbar-light navbar-fixed-top" style="background-color: #e3f2fd;">
        <div class="container-fluid px-5">
          <h1 class="navbar-brand mb-0 h1" style="font-weight: bold;" @click="scrollToSection('Welcome')">
            <i class="bi bi-playstation"></i> Nattawut Supapat
          </h1>

          <div class="collapse navbar-collapse justify-content-end" id="navbarNav">
            <ul class="navbar-nav">
              <li class="nav-item">
                <a class="nav-link active" aria-current="page" @click="scrollToSection('Welcome')">
                  <strong>Welcome</strong>
                </a>
              </li>
              <li class="nav-item">
                <a class="nav-link" @click="scrollToSection('AboutMe')">
                  <strong>About</strong>
                </a>
              </li>
              <li class="nav-item">
                <a class="nav-link" @click="scrollToSection('Education')">
                  <strong>Education</strong>
                </a>
              </li>
              <li class="nav-item">
                <a class="nav-link" @click="scrollToSection('Record')">
                  <strong>Record</strong>
                </a>
              </li>
              <li class="nav-item">
                <a class="nav-link" @click="scrollToSection('Skills')">
                  <strong>Skills</strong>
                </a>
              </li>
            </ul>
          </div>
        </div>
      </nav>
    </section>

    <section class="bg-light my-5" id="Welcome" ref="Welcome">
      <Welcome />
    </section>
    
    <section class="bg-light my-5" id="AboutMe" ref="AboutMe">
      <AboutMe />
    </section>

    <section class="bg-light my-5" id="Hobbies">
      <TheHobbies />
    </section>

    <section class="bg-light my-5" id="Education" ref="Education">
      <Education />
    </section>

    <section class="bg-light my-5" id="Record" ref="Record">
      <RecordPage />
    </section>

    <section class="bg-light my-5" id="Skills" ref="Skills">
      <Skills />
    </section>
     <!--- footter --->
  <section class="container-fluid py-3 bg-secondary">
    <h1 class = "text-white text-center">Contact</h1>
    <p class="text-white text-center">@ 2024 KU-SRC Computer Science.</p>
    <p class="text-white text-center">@ FB : Nattawut Supapat. @ Tell : 063-082-1353</p>
  </section>
  </div>
</template>

<script>
import Welcome from "./components/Welcome.vue";
import AboutMe from "./components/AboutMe.vue";
import TheHobbies from "./components/TheHobbies.vue";
import Education from "./components/Education.vue";
import Skills from "./components/Skills.vue";
import RecordPage from "./components/RecordPage.vue";

export default {
  name: "App",
  components: {
    Welcome,
    AboutMe,
    TheHobbies,
    Education,
    Skills,
    RecordPage,
  },
  methods: {
    scrollToSection(sectionId) {
      const element = document.getElementById(sectionId);
      if (element) {
        element.scrollIntoView({ behavior: "smooth" });
      }
    },
  },
};
</script>

<style scoped>
.nav-link {
  position: relative;
  cursor: pointer;
}

.hover-icon {
  display: none;
  position: absolute;
  left: 100%;
  margin-left: 5px;
}

.nav-link:hover .hover-icon {
  display: inline-block;
}
</style>
