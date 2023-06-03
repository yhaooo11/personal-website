<script setup>
import Contents from './components/Contents.vue';
import Main from './components/Main.vue';
import Links from './components/Links.vue';
import About from './components/About.vue';
import ExperienceCard from './components/ExperienceCard.vue';
import EducationCard from './components/EducationCard.vue';
import IconFile from './components/icons/IconFile.vue'
import ProjectCard from './components/ProjectCard.vue';
</script>

<template>
  <div class="container">
    <div class="column left">
      <Main />
      <Contents @scrollto="goto" :section="section" />
      <Links />
    </div>

    <main class="column right">
      <div ref="about">
        <About />
      </div>
      <h2 ref="experience">Experience</h2>
      <ExperienceCard 
        startDate="Jan. 2023"
        endDate="Present"
        role="Jr. Full Stack Developer"
        company="Verto Health"
        description="Deliver high-quality, robust production code for a diverse array of projects for clients. Provide leadership within engineering department through close collaboration, knowledge shares, and mentorship."
        :skills="['Vue', 'Angular', 'Ruby on Rails', 'Python', 'JavaScript', 'TypeScript', 'Git']"
      >
      </ExperienceCard>
      <ExperienceCard 
        startDate="Sept. 2023"
        endDate="Jan. 2023"
        role="Teaching Assistant"
        company="UBC Computer Science"
        description="Led weekly programming labs for over 60 students for CPSC 110 (Computation, Programs, and Programming). Explained programming concepts in Racket including recursion, data types, and systematic code design"
        :skills="['Racket', 'Teaching', 'Leadership', 'Programming Concepts']"
      >
      </ExperienceCard>
      <div class="resume">
        <a class="resume-link">View Full Resume</a>
        <IconFile class="resume-icon"></IconFile>
      </div>
      <h2 ref="education">Education</h2>
      <EducationCard
        gradDate="Expected Graduation May 2026"
        school="University of British Columbia"
        degree="Bachelor of Science in Computer Science and Statistics"
        gpa="4.0/4.0"
        :relevantCourses="['CPSC 110 (Intro to Programming)', 'CPSC 210 (OOP)', 'CPSC 221 (DSA)']"
      >
      </EducationCard>
      <h2 ref="projects">Projects</h2>
      <ProjectCard
        imgName="website-bright.png"
        name="Personal Website"
        link="https://github.com/yhaooo11/ytpv"
        description="This website you are on right now!"
        :techs="['Vue', 'CSS', 'JavaScript']"
      >
      </ProjectCard>
      <ProjectCard
        imgName="ytpv.png"
        name="ytpv (YouTube Playlist Video Maker)"
        link="https://github.com/yhaooo11/ytpv"
        description="A web app that allows you to create and download your own playlist videos by combining multiple youtube videos into one."
        :techs="['React', 'Flask', 'Python', 'JavaScript', 'Docker']"
      >
      </ProjectCard>
      <ProjectCard
        imgName="queue.webp"
        name="EasyQueue"
        link="https://github.com/yhaooo11/EasyQueue"
        description="A free online queue maker website. Simply create an account and create your own queue. Joining is as simple as clicking a link."
        :techs="['React', 'Express', 'SocketIO', 'MongoDB', 'Bootstrap']"
      >
      </ProjectCard>
    </main>
  </div>
</template>

<script>
export default {
  created () {
    window.addEventListener('scroll', this.handleScroll);
  },
  unmounted () {
    window.removeEventListener('scroll', this.handleScroll);
  },
  data() {
    return {
      section: 0
    }
  },
  methods: {
    handleScroll (event) {
      let scroll = window.top.scrollY;
      var about = this.$refs['about'];
      var experience = this.$refs['experience'];
      var education = this.$refs['education'];
      var projects = this.$refs['projects'];

      if (scroll < experience.offsetTop) {
        this.section = 0;
      } else if (scroll >= experience.offsetTop && scroll < education.offsetTop) {
        this.section = 1;
      } else if (scroll >= education.offsetTop && scroll < projects.offsetTop - 225) {
        this.section = 2;
      } else {
        this.section = 3;
      }
    },
    goto(refName) {
      var element = this.$refs[refName];
      var top = refName === 'about' ? 0 : element.offsetTop
      window.scrollTo({
        top: top,
        behavior: 'smooth'
      });
    }
  }
}
</script>

<style scoped>
.container {
  display: flex;
  gap: 1rem;
  justify-content: space-between;
  padding: 4rem 8rem;
}

@media (max-width: 800px) {
  .container {
    flex-direction: column;
  }
}

.column {
  flex: 1;
  width: 50%;
}

.right {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  gap: 4rem;
}

.left {
  display: flex;
  flex-direction: column;
  gap: 6rem;
  height: fit-content;
  position: sticky;
  top: 4rem;  
}

.resume {
  transition: all .5s ease-in;
  color: #e6edf8;
  font-size: 1.3rem;
  font-weight: 500;
  text-decoration: none;
  display: flex;
  gap: 1rem;
}

.resume-link:hover {
  text-decoration:underline;
  cursor: pointer;
}

.resume-icon {
  width: 1rem;
}

h2 {
  color: #95bae4;
  font-size: 2rem;
  font-weight: 600;
}

main {
  margin-bottom: 5rem;
}
</style>