<template>
  <div>
    <div class="main-view" :class="{ hidden: scrolledDown }">
      <div class="sider sidebar">
        <div class="holder">
          <div class="xx" role="navigation" aria-labelledby="main-nav-heading">
            <div class="title"></div>
            <a class="listitem" href="#intro">Intro</a>
            <a class="listitem" href="#Intro">About Me</a>
            <a class="listitem" href="#projects">Projects</a>
            <a class="listitem" href="#education">Education</a>
            <a class="listitem" href="#experience">Experience</a>
            <a class="listitem" href="#contact">Get in Touch</a>
            <br />
            <div class="contact">
              <a target="_blank" href="mailto:njpietrow@gmail.com"
                >njpietrow@gmail.com</a
              >
              <br />
              <a target="_blank" href="Resume_NickPietrow.pdf">Resume</a>
            </div>
          </div>
        </div>
      </div>
      <div class="main">
        <section id="intro">
          <div class="txt">
            <h1>
              Hi, I'm Nick Pietrow.
              <br />
              I'm a consultant turned software engineer who loves solving
              interesting problems.
            </h1>
            <br />
            <a href="#Intro">About Me <Fa fa="arrow-down" /></a>
          </div>
        </section>
        <section id="Intro" aria-labelledby="intro-heading">
          <h2 id="intro-heading">About Me</h2>
          <img id="avatar" src="/images/avatar.jpeg" alt="avatar" />
          <span>
            I've always enjoyed tackling puzzles and challenging myself to think
            outside the box, so I consider myself lucky that software
            engineering as a career has consistently pushed me to learn new
            skills, meet amazing people, and bring ideas to life. <br /><br />
            While not coding, you can find me either buried in a game of chess,
            playing basketball in my local rec league, or surfing in Malibu.
          </span>
        </section>
        <section id="projects" aria-labelledby="projekte-heading">
          <h2 id="projekte-heading">Projects</h2>
          <div class="cards">
            <div class="card-col">
              <Card :item="projects[0]" :txt="select" />
              <Card :item="projects[1]" :txt="select" />
            </div>
            <div class="card-col">
              <Card :item="projects[2]" :txt="select" />
            </div>
          </div>
        </section>
        <section id="education">
          <h2 id="lebenslauf-heading">Education</h2>
          <ul>
            <li>
              <img src="images/aa-logo.png" alt="" />
              <div class="stack">
                <a target="_blank" href="https://www.appacademy.io/"
                  >App Academy</a
                >
                <span>Full Stack Web Development (2022)</span>
              </div>
            </li>
            <li>
              <img src="images/usc-logo.jpeg" alt="" />
              <div class="stack">
                <a target="_blank" href="https://about.usc.edu/"
                  >University of Southern California</a
                >
                <span
                  >BS Business Administration, Minor Computer Science (2019)
                </span>
              </div>
            </li>
            <li></li>
          </ul>
        </section>
        <section id="experience" aria-labelledby="lebenslauf-heading">
          <h2 id="lebenslauf-heading">Experience and Skills</h2>
          <div class="lebenslauf">
            <h3>Work Experience</h3>
            <div class="cont" v-for="i in experience" :key="i.ort">
              <span>{{ i.datum }}</span>
              <span>{{ i.extra }}</span>
              <span>{{ i.titel }}</span>
              <span>{{ i.ort }}</span>
              <span>{{ i.txt }}</span>
            </div>
          </div>
          <br />
          <a target="_blank" href="Resume_NickPietrow.pdf">
            <Fa fa="file-pdf" /> Resume
          </a>
          <br />
          <a target="_blank" href="https://www.linkedin.com/in/nickpietrow/">
            <Fa fa="linkedin" /> LinkedIn
          </a>
          <br /><br /><br />
          <div class="lebenslauf">
            <h3>Skills</h3>
            <ul class="buzzwords">
              <li><span>React</span></li>
              <li><span>Redux</span></li>
              <li><span>JavaScript</span></li>
              <li><span>HTML</span></li>
              <li><span>CSS</span></li>
              <li><span>Node.js</span></li>
              <li><span>Ruby</span></li>
              <li><span>Ruby on Rails</span></li>
              <li><span>Python</span></li>
              <li><span>Java</span></li>
              <li><span>Sass</span></li>
              <li><span>SQL</span></li>
              <li><span>Mongo DB</span></li>
              <li><span>AWS S3</span></li>
              <li><span>Google Maps API</span></li>
              <li><span>FaceMesh API</span></li>
              <li><span>Mongoose</span></li>
              <li><span>Express.js</span></li>
              <li><span>SQL</span></li>
              <li><span>PostgreSQL</span></li>
              <li><span>SQLite3</span></li>
              <li><span>Heroku</span></li>
              <li><span>Git</span></li>
              <li><span>Webpack</span></li>
              <li><span>npm</span></li>
              <li><span>RSpec</span></li>
              <li><span>Capybara</span></li>
              <li><span>Jasmine</span></li>
              <li><span>MERN</span></li>
              <li><span>jQuery</span></li>
              <li><span>JBuilder</span></li>
            </ul>
          </div>
        </section>
        <section id="contact" aria-labelledby="kontakt-heading">
          <h2 id="kontakt-heading">Contact</h2>
          <br />
          <Fa fa="envelope-o" /> njpietrow@gmail.com <br />
          <Fa fa="map-marker" /> Los Angeles, CA <br />
          <br />
          <a target="_blank" href="Resume_NickPietrow.pdf">
            <Fa fa="file-pdf" /> Resume
          </a>
          <br />
          <a target="_blank" href="https://github.com/njpietrow">
            <Fa fa="github" /> GitHub</a
          >
          <br />
          <a target="_blank" href="https://www.linkedin.com/in/nickpietrow/">
            <Fa fa="linkedin" /> LinkedIn
          </a>
          <br />
          <a target="_blank" href="https://angel.co/u/nick-pietrow">
            <Fa fa="angellist" />AngelList</a
          >
        </section>
      </div>
    </div>
    <PopOver :selected="selected" :closeWindow="closePopOver" />
  </div>
</template>

<script>
import Card from './globals/Card.vue';
import Fa from './globals/Fa.vue';
import PopOver from './PopOver.vue';

export default {
  components: {
    Card,
    Fa,
    PopOver,
  },
  data: () => ({
    experience: [
      {
        datum: 'July 2019 – Dec 2021',
        extra: 'True Partners Consulting',
        titel: 'Senior Consultant, Unclaimed Property',
        ort: 'Tax Automation, Project Management',
        txt: '',
      },
      {
        datum: 'May 2018 – Aug 2018',
        extra: 'RingCentral, Inc.',
        titel: 'Accounting Intern',
        ort: 'International Accounting, Tax Automation',
        txt: '',
      },
      {
        datum: 'May 2017 – Aug 2017',
        extra: 'Sands Investment Group',
        titel: 'Summer Analyst',
        ort: 'Real Estate Analysis, Web Scraping',
        txt: '',
      },
      {
        datum: 'May 2016 – Jun 2016',
        extra: 'Popping Commons, Inc.',
        titel: 'Product Analyst',
        ort: 'User Experience, Market Research',
        txt: '',
      },
    ],
    projects: [
      {
        id: 0,
        images: [
          {
            img: 'https://media.giphy.com/media/71fFzrI9JdXF6fdeGd/giphy.gif',
          },
          {
            img: '/images/verve2.png',
          },
          {
            img: 'https://media.giphy.com/media/2b8x8TifiH8fLJt0e2/giphy.gif',
          },
          {
            img: 'https://media.giphy.com/media/4XYGnn0hgnIWNbUyF1/giphy.gif',
          },
        ],
        titel: 'The Verve',
        tags: ['React', 'Redux', 'Ruby on Rails', 'PostgreSQL'],
        demo: 'https://the-verve.herokuapp.com/#',
        source: 'https://github.com/njpietrow/The-Verve#readme',
      },
      {
        id: 1,
        images: [
          {
            img: 'https://media.giphy.com/media/zHyQhXUpEMun1Mz6Pn/giphy.gif',
          },
          {
            img: '/images/hoppers1.png',
          },
          {
            img: 'https://media.giphy.com/media/hJai6xoHx2C7KHFKic/giphy.gif',
          },
          {
            img: 'https://media.giphy.com/media/xs3l47FQu2yrMSgEaI/giphy.gif',
          },
          {
            img: 'https://media.giphy.com/media/LS4zK20qBpOypG65Ub/giphy.gif',
          },
        ],
        titel: 'Hoppers',
        tags: ['mongoDB', 'Express', 'React', 'NodeJS'],
        demo: 'https://go-hoppers.herokuapp.com/',
        source: 'https://github.com/JonJWong/Hoppers#readme',
      },
      {
        id: 2,
        images: [
          {
            img: 'https://media.giphy.com/media/d7DzvSBdBiYGQulmFi/giphy.gif',
          },
          {
            img: '/images/app_pic.png',
          },
          {
            img: 'https://raw.githubusercontent.com/njpietrow/Filter.io/main/assets/landmarks.png',
          },
        ],
        titel: 'Filter.io',
        tags: ['Vanilla JavaScript', 'FaceMesh API', 'Sass'],
        demo: 'https://njpietrow.github.io/Filter.io/',
        source: 'https://github.com/njpietrow/Filter.io#readme',
      },
    ],
    selected: null,
  }),
  mounted() {
    window.onscroll = this.lodash.debounce(this.scrollcalc, 5);
    this.scrollcalc();
    let anchorlinks = document.querySelectorAll('a[href^="#"]');

    for (let item of anchorlinks) {
      item.addEventListener('click', (e) => {
        let hashval = item.getAttribute('href');
        let target = document.querySelector(hashval);
        target.scrollIntoView({
          behavior: 'smooth',
          block: 'start',
        });
        history.pushState(null, null, hashval);
        e.preventDefault();
      });
    }
  },
  methods: {
    select: function (id) {
      this.selected = this.projects.find((x) => x.id === id);
    },
    closePopOver() {
      this.selected = null;
    },
    scrollcalc() {
      let mainNavLinks = document.querySelectorAll('.xx a');
      let fromTop = document.documentElement.scrollTop;
      let navbarHeight = 200;

      mainNavLinks.forEach((link) => {
        if (link.hash == '') return;

        let section = document.querySelector(link.hash);
        if (section == null) return;
        if (
          section.offsetTop <= fromTop + window.innerHeight &&
          section.offsetTop + section.offsetHeight > fromTop + navbarHeight
        ) {
          link.classList.add('current');
          let allCurrents = document.querySelectorAll('.current');
          let allFirsts = document.querySelector('.first');
          if (allFirsts != null) {
            allFirsts.classList.remove('first');
          }
          allCurrents[0].classList.add('first');
        } else {
          link.classList.remove('current');
        }
      });
    },
  },
  props: {
    scrolledDown: Boolean,
  },
};
</script>

<style lang="scss" scoped>
.buzzwords li {
  // display: flex;
  display: inline;
  word-break: break-all;
  line-height: 24px;
  font-weight: 500;
  font-size: 14px;
  margin: 0px 6px;
  border-radius: 4px;
  margin-bottom: 10px;
  padding: 4px 0px;
  display: inline-block;
  // justify-content: center;
}
.buzzwords li span {
  border: 1px solid #0bceaf;
  padding: 4px 10px;
  border-radius: 4px;
}
.buzzwords {
  display: flex;
  justify-content: center;
  width: 80%;
  flex-wrap: wrap;
  padding-left: 0px;
}
#education img {
  height: 40px;
  padding-right: 12px;
}
#education ul {
  padding-left: 0;
}
#education li {
  display: flex;
  align-items: center;
  padding-bottom: 12px;
  a {
    color: #fff;
    text-underline-offset: 3px;
    transition: text-decoration 0.2s ease-in;
    // padding-bottom: 10px;
    text-decoration-style: dotted;
  }
  a:hover {
    text-decoration-color: #0bceaeda;
  }
  span {
    font-size: 0.9rem;
    color: #a1a1a1;
  }
}

#intro {
  .txt {
    a {
      display: none;
      text-decoration: none;
      color: white;
    }
  }
}
@media screen and (max-width: 680px) {
  .cards {
    display: block !important;
  }
  .card {
    width: 100% !important;
    height: 33rem !important;
  }
  #intro {
    .txt {
      a {
        display: hidden;
      }
    }
  }
  .hidden {
    #intro {
      .txt {
        a {
          display: block;
        }
      }
    }
  }
  .cont {
    grid-template-areas:
      'datum'
      'extra'
      'titel'
      'ort'
      'txt' !important;
    grid-template-columns: 100% !important;
  }
  .txt h1 {
    font-size: 7vw !important;
  }
}
#contact,
#experience {
  a {
    color: white;
    i {
      font-size: 0.9rem;
    }
  }
  a:hover {
    color: hsl(0deg 0% 63%);
  }
}
.bildungsweg,
.lebenslauf {
  h3 {
    font-size: 0.9rem;
  }
  cursor: default;
}
.cont {
  display: grid;
  grid-template-areas:
    'datum titel'
    'extra ort'
    '. txt';
  grid-template-columns: 11rem 370px;
  gap: 0rem 1rem;
  margin-bottom: 1.3rem;
  span:nth-child(1) {
    grid-area: datum;
    font-weight: 600;
    font-size: 0.9rem;
    color: hsl(0deg 0% 63%);
    letter-spacing: -0.02rem;
  }
  span:nth-child(2) {
    grid-area: extra;
    font-size: 0.87rem;
    color: hsl(0deg 0% 63%);
    letter-spacing: -0.02rem;
  }
  span:nth-child(3) {
    grid-area: titel;
  }
  span:nth-child(4) {
    grid-area: ort;
    font-size: 0.9rem;
    color: hsl(0deg 0% 63%);
  }
  span:nth-child(5) {
    grid-area: txt;
    font-size: 0.9rem;
    color: hsl(0deg 0% 63%);
  }
}

.contact {
  // margin: 2rem 0rem;
  display: flex;
  flex-flow: column;
  gap: 0.7rem;
  width: 100%;
  transition: opacity 0.3s;
  a {
    text-decoration: none;
    color: var(--txt-med);
    padding: 0rem 1.5rem;
  }
}
.contact {
  a:hover {
    color: white;
  }
}
#Intro {
  a {
    color: var(--accent-1);
    text-decoration: none;
    i {
      margin-left: 0.4rem;
    }
  }
}
section {
  padding: 6rem 0rem;
  &:empty {
    display: none;
  }
  span {
    display: block;
    max-width: 550px;
  }
}
.mainitem-active {
  border-radius: 6px;
  background: hsl(220 100% 71% / 0.11);
  color: hsl(220 100% 53% / 1) !important;
  margin-bottom: 0.3rem;
}
.title {
  font-size: 12px !important;
  font-weight: 700 !important;
  margin: 0.2em 0em 1rem 0rem;
  text-transform: capitalize;
  color: #b2b2b2;
  text-transform: uppercase;
  letter-spacing: 0.02rem;
  width: 100%;
  text-align: center;
}
.xx {
  display: flex;
  flex-flow: column;
  align-items: self-end;
  gap: 0.7rem;
  a {
    transition: min-width 0.3s, border 0.3s, padding 0.3s, box-shadow 0.3s,
      background 0.15s;
    width: fit-content;
    min-width: 210px;
    max-width: -webkit-fill-available;
  }
}
.listitem:nth-child(2).first {
  background: var(--accent-1);
}
.listitem:nth-child(3).first {
  background: var(--accent-2);
}
.listitem:nth-child(4).first {
  background: var(--accent-3);
}
.listitem:nth-child(5).first {
  background: var(--accent-4);
}
.listitem:nth-child(6).first {
  background: var(--accent-5);
}
.listitem:nth-child(7).first {
  background: var(--accent-6);
}
.listitem:hover {
  background-color: hsla(0, 0%, 80%, 0.15);
}
.listitem {
  text-decoration: none;
  display: block;
  padding: 0.75rem 1.8rem;
  margin-right: 1rem;
  color: white;
  font-size: 0.95em;
  cursor: pointer;
  transition: border 0.3s, padding 0.3s, box-shadow 0.3s, background 0.15s;
  border-left: 2px solid transparent;
  font-weight: 500;
  border-radius: 0.4rem;
}
.mainitem {
  padding: 0.5rem 0.5rem;
}
.current {
  border-left: 6px solid #ffffff1c;
  // box-shadow: 0px 0px 0px 0px black;
}
.first {
  color: black;
  color: black !important;
  padding-left: 2rem;
  font-weight: 600;
  transform-origin: left;
  animation: pop 0.25s ease-out;
}
@keyframes pop {
  35% {
    transform: scale(1.05);
  }
  75% {
    transform: scale(0.96);
  }
  100% {
    transform: scale(1);
  }
}
</style>

<style lang="scss" scoped>
.card-col:nth-child(2) {
  margin-top: 12rem;
}
.cards {
  display: flex;
  gap: 1.7rem;
}
.card-col {
  display: flex;
  flex-flow: column;
  gap: 1.7rem;
}

.sidebar,
.sideoptions {
  transition: width 0.3s;
}
@media screen and (max-width: 1300px) {
  .main-view {
    grid-template: 'siderbar main main';
  }
  .sideoptions {
    display: none;
  }
}
@media screen and (max-width: 1023px) {
  .main-view {
    grid-template: 'main main main' !important;
    grid-template-columns: 1fr !important;
    width: auto !important;
  }
  .card-col:nth-child(2) {
    margin-top: 2rem !important;
  }
  .sidebar {
    display: none;
  }
}

.holder {
  scrollbar-color: #bebebe transparent;
  scrollbar-width: thin;
}
.holder:hover {
  scrollbar-color: #bebebe #f2f2f2;

  scrollbar-width: revert !important;
}

.holder::-webkit-scrollbar {
  width: 15px;
  padding: 10px;
}

.holder::-webkit-scrollbar-thumb {
  border-radius: 10px;
  /* background-color: #bebebe; */
  border: 5px solid transparent;
  background-clip: content-box;
}

.sider:hover .holder::-webkit-scrollbar {
  width: 15px;
}

.sider:hover .holder::-webkit-scrollbar-track {
  border-radius: 10px;
}

.sider:hover .holder::-webkit-scrollbar-thumb {
  border: 0;
  border-radius: 10px;
}

.sider:hover .holder::-webkit-scrollbar-thumb:hover {
  background: #818b99;
}
.sider {
  height: 100%;
  width: 310px;
}
.holder {
  padding: 1rem;
  position: -webkit-sticky;
  position: sticky;
  top: 60px;
  height: calc(100vh - 90px);
  overflow-y: auto;
}
.sidebar {
  justify-self: right;
}

.link .fas {
  font-size: 0.8rem;
}

.filters > .text {
  padding: 0.5em 0em;
  display: block;
}
.filters > .text > input {
  width: 125px;
  border: 0;
  background: 0;
  margin: 0rem 0.3rem;
  border-bottom: 1px solid gray;
}
.filters {
  margin: 2rem 0rem;
}

h2 {
  font-size: 1rem;
  color: var(--txt-med);
  margin-bottom: 2rem;
  cursor: default;
}
.main-view {
  display: grid;
  grid-template: 'siderbar main';
  grid-template-columns: 1fr minmax(600px, 770px);
  width: fit-content;
  margin-left: auto;
  margin-right: auto;
  z-index: 100;
}
div > .main {
  max-width: 1000px;
  margin: auto;
  padding: 2rem;
  box-sizing: border-box;
  line-height: 1.6;
  color: var(--txt);
  padding: 1.5rem 1.5rem 80vh 1.5rem;
  width: 100%;
  z-index: 100;
}
</style>
<style scoped lang="scss">
.txt h1 {
  font-size: 3rem;
  margin: 0.2rem 0;
  line-height: 1.3;
  max-width: 600px;
}
.main-view {
  transition: background 0.3s;
  section {
    transition: opacity 0.3s;
  }
}

.main-view,
.main-view {
  .main .holder,
  .sider {
    transition: background 0.3s;
  }
}
.hidden {
  .xx {
    a {
      transition: min-width 0.3s;
      min-width: 0px;
      width: fit-content;
    }

    .title {
      opacity: 0;
    }
    .listitem {
      border: 0;
      color: black;
    }
    .listitem:nth-child(2) {
      background: var(--accent-1);
    }
    .listitem:nth-child(3) {
      background: var(--accent-2);
    }
    .listitem:nth-child(4) {
      background: var(--accent-3);
    }
    .listitem:nth-child(5) {
      background: var(--accent-4);
    }
    .listitem:nth-child(6) {
      background: var(--accent-5);
    }
    .listitem:nth-child(7) {
      background: var(--accent-6);
    }
    .listitem:hover {
      background: #fbfbfb;
    }
  }
  .contact,
  section {
    opacity: 0;
  }
  .main,
  .holder,
  .sider {
    background: transparent !important;
  }
  background: transparent !important;
  box-shadow: unset !important;
}
#intro {
  opacity: 100;
}
#avatar {
  border-radius: 50%;
  width: 150px;
  border: 4px solid rgb(49, 49, 49);
  margin-bottom: 40px;
}
</style>
