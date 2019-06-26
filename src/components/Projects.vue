<template>
  <div class="divProjects" id="projects">
    <h3 class="projectsMainHeading">Projects</h3>
    <div
      class="divProject"
      v-for="item in projects"
      :key="item.key"
      :class="item.key%2==1?'right':'left'"
    >
      <a :href="item.link" target="blank">
        <div class="divProjectImages" :class="item.class"></div>
        <div class="divProjectContent">
          <div class="divProjectName">{{item.name}}</div>
          <div class="divProjectDesc">{{item.desc}}</div>
        </div>
      </a>
    </div>
  </div>
</template>

<script>
export default {
  name: "Projects",
  data() {
    return {
      projects: [
        {
          key: 1,
          name: "Bitlab Academy",
          desc:
            "Bitlab Academy is Educational product of  Baseblock, an innovative educational institution, that offers several different industry-leading and in-demand educational programs, following alternative project-based learning model. I have been tasked to develop the website using VueJS as a front-end and NodeJS as a back end.",
          class: "bitlab",
          link: "https://bitlabacademy.netlify.com"
        },
        // {
        //   key: 2,
        //   name: "Bitstat",
        //   desc:
        //     "Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book.",
        //   class: "bitstat"
        // },
        {
          key: 2,
          name: "Ethereum Smart Contract",
          desc:
            "Developed an Ethereum smart contract by using Solidity and web3.js which can be used for crowdsales which can be used to transfer funds and also has a time based bonus structure.",
          class: "bitstat",
          link:
            "https://rinkeby.etherscan.io/token/0x275a5b346599b56917e7b1c9de019dcf9ead861a"
        },
        {
          key: 3,
          name: "Baseblock",
          desc:
            "Software has become an essential tool for every business in the world, yet most businesses don’t have access to quality software development at a reasonable cost. Businesses with access to quality software have hundreads of times more leverage than those without. At Baseblock, we aim to develop high quality software in reasonable budget.",
          class: "baseblock",
          link: "https://baseblock.netlify.com/"
        },
        {
          key: 4,
          name: "Brand Tracker",
          desc:
            "This is a tool to track the Brand Value across multiple regions and can be compared with multiple metrics and competitors. This tool is developed by using ASP.NET MVC, JQuery and highcharts.js",
          class: "brandtracker"
        }
      ]
    };
  }
};
</script>

<style scoped>
.divProjects {
  padding: 0 16%;
  padding-bottom: 30px;
  background-color: #f5f5f5;
}
.projectsMainHeading {
  font-weight: 900;
  font-size: 40px;
  text-transform: uppercase;
  color: rgba(0, 0, 0, 0.1);
  margin: 0;
  background: linear-gradient(72.2deg, #0077b5 -8.9%, #32a9e7 108.42%),
    rgba(0, 0, 0, 0.1);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  width: 189px;
}
.divProject {
  background: #ffffff;
  border-radius: 8px;
  height: 400px;
  margin-bottom: 89px;
  position: relative;
  background: #e1e1e1;
}
.divProject:last-child {
  margin-bottom: 0;
}
.divProjectContent {
  background: #f5f5f5;
  width: 500px;
  height: 230px;
  position: absolute;
  top: 85px;
  padding: 24px;
  cursor: pointer;
  /* right: 0; */
}
.divProjectContent:after {
  content: " ";
  background-image: url("../assets/arrow.svg");
  right: 50px;
  bottom: 30px;
  position: absolute;
  width: 50px;
  height: 8px;
  background-repeat: no-repeat;
  transition: all 0.5s;
}
.divProjectContent:hover:after {
  right: 30px;
}
.left .divProjectContent {
  left: 0;
  border-top-right-radius: 8px;
  border-bottom-right-radius: 8px;
}
.right .divProjectContent {
  right: 0;
  border-top-left-radius: 8px;
  border-bottom-left-radius: 8px;
}
.right {
}
.left {
}
.divProjectName {
  font-weight: 500;
  line-height: 21px;
  font-size: 20px;
  text-transform: uppercase;
}
.divProjectDesc {
  margin-top: 20px;
  line-height: 18px;
  font-size: 14px;
}
.divProjectImages {
  height: 100%;
  position: absolute;
  width: 550px;
  background-size: 90%;
  background-repeat: no-repeat;
  background-position: 0% -65%;
  /* background: */
}
.right .divProjectImages {
  left: 75px;
}
.left .divProjectImages {
  right: 75px;
  background-position: 15% -65%;
}
.bitlab {
  background-image: url("../assets/bitlab.png");
}
.baseblock {
  background-image: url("../assets/baseblock.png");
}
.bitstat {
  background-image: url("../assets/bitstat.png");
  /* background-position: 15% 50% !important; */
}
.brandtracker {
  background-image: url("../assets/brandtracker.png");
}
a {
  color: #000;
}
@media (max-width: 1440px) {
  .divProjectImages {
    width: 450px;
    background-position: 0% 150%;
  }
  .divProjectContent {
    width: 400px;
  }
  .left .divProjectImages {
    background-position: 50% 150%;
  }
}
@media (max-width: 1366px) {
  .divProjectImages {
    background-position: -50% 150%;
  }
  .left .divProjectImages {
    background-position: 120% 150%;
  }
}
@media (max-width: 1200px) {
  .divProjectImages {
    background-size: 80%;
    background-position: -50% 70%;
    width: 350px;
  }
  .right .divProjectImages {
    left: 25px;
  }
  .left .divProjectImages {
    background-position: 110% 65%;
    right: 25px;
  }
}
@media (max-width: 768px) {
  .divProjects {
    padding: 0 10%;
  }
  .right .divProjectContent,
  .left .divProjectContent {
    width: 100%;
    height: 200px;
    background: #fff;
    border-radius: 8px;
    top: auto;
    bottom: 0;
    right: 0;
    left: auto;
  }
  .divProjectDesc {
    overflow: hidden;
    position: relative;
    line-height: 1.2em;
    max-height: 6em;
    /* text-align: justify; */
    margin-right: -1em;
    padding-right: 24px;
    -webkit-line-clamp: 5;
    -webkit-box-orient: vertical;
    overflow: hidden;
    text-overflow: ellipsis;
    display: -webkit-box;
  }
  .divProjectDesc:before {
    /* content: "...";
    position: absolute;
    right: 35px;
    bottom: 5px; */
  }
  .divProjectDesc:after {
    /* content: "";
    position: absolute;
    right: 0;
    width: 1em;
    height: 1em;
    margin-top: 0.2em;
    background: white; */
  }
  .divProject {
    margin-bottom: 30px;
    height: 500px;
  }
  .divProjectImages {
    left: 0 !important;
    right: auto !important;
    height: 200px;
    background-position: 50% 20px !important;
    width: 100%;
    background-size: 80%;
    left: 0 !important;
    right: auto !important;
    height: 300px;
    background-position: 50% 0% !important;
    width: 100%;
    background-size: 70%;
  }
}
@media (max-width: 576px) {
  .divProjectImages {
    left: 0 !important;
    right: auto !important;
    height: 200px;
    background-position: 50% 20px !important;
    width: 100%;
    background-size: 80%;
  }
  .divProject {
    height: 400px;
  }
}
</style>
