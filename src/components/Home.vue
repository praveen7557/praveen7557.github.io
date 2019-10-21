<template>
  <div class="divHome">
    <div class="divHomePreview">
      <div class="divHeader">
        <div class="FL divName">Praveen Bolla.</div>
        <div class="FR divLinks">
          <span class="divLink">
            <a href="#">About</a>
          </span>
          <span class="divLink">
            <a
              href="https://drive.google.com/uc?export=download&id=19URTjnF2r6rnReQu9b4LzzUToZmLceVC"
            >Resume</a>
          </span>
          <span class="divLink">
            <a href="#projects">Projects</a>
          </span>
          <span class="divLink">
            <a href="#contact">Contact</a>
          </span>
        </div>
        <a href="mailto:praveenb0800@gmail.com" class="mailLink">
          <div class="mailID">praveenb0800[at]gmail.com</div>
        </a>
      </div>
      <div class="divAbout">
        <div class="divImage divMobile"></div>
        <div class="divIntro">
          <h2 class="mainHeading">Hi, I am Praveen Bolla.</h2>
          <p class="mainLabel">Currently working as a Senior Software Developer at West Agile Labs.</p>
          <div class="divActionButtons">
            <a href="https://www.linkedin.com/in/praveen-bolla-2a6356b0/">
              <div class="divLinkedIn">
                <span class="linkedinImg"></span>LinkedIn
              </div>
            </a>
            <a href="mailto:praveenb0800@gmail.com">
              <div class="mailID divDesktop">praveenb0800[at]gmail.com</div>
            </a>
            <a
              href="https://drive.google.com/uc?export=download&id=19URTjnF2r6rnReQu9b4LzzUToZmLceVC"
            >
              <div class="mailID divMobile">Download Resume</div>
            </a>
          </div>
        </div>
        <div class="divImage divDesktop"></div>
      </div>
    </div>
    <div class="divSkills">
      <div
        class="divSkill"
        :title="item.name"
        :style="{'background-image':item.bg,'width':item.width,'height':item.height}"
        v-for="item in skills"
        :key="item.key"
      ></div>
    </div>
    <Experience />
    <Projects />
    <Contact />
  </div>
</template>

<script>
import Projects from "./Projects.vue";
import Contact from "./Contact.vue";
import Experience from "./Experience.vue";

export default {
  name: "Home",
  components: {
    Projects,
    Contact,
    Experience
  },
  data() {
    return {
      skills: [
        {
          key: 1,
          name: "HTML",
          bg: 'url("' + require("../assets/html.svg") + '")',
          width: "70px",
          height: "70px"
        },
        {
          key: 3,
          name: "CSS",
          bg: 'url("' + require("../assets/css.svg") + '")',
          width: "70px",
          height: "70px"
        },
        {
          key: 6,
          name: "JavaScript",
          bg: 'url("' + require("../assets/js.svg") + '")',
          width: "70px",
          height: "70px"
        },
        {
          key: 9,
          name: "Vue.js",
          bg: 'url("' + require("../assets/vue.png") + '")',
          width: "70px",
          height: "70px"
        },
        {
          key: 4,
          name: "React.js",
          bg: 'url("' + require("../assets/react.svg") + '")',
          width: "70px",
          height: "70px"
        },
        {
          key: 8,
          name: "Node.js",
          bg: 'url("' + require("../assets/node.svg") + '")',
          width: "70px",
          height: "70px"
        },
        {
          key: 7,
          name: "MongoDB",
          bg: 'url("' + require("../assets/mongo.svg") + '")',
          width: "160px",
          height: "70px"
        },
        {
          key: 5,
          name: "MySQL",
          bg: 'url("' + require("../assets/mysql.svg") + '")',
          width: "115px",
          height: "70px"
        },
        {
          key: 10,
          name: "GraphQL",
          bg: 'url("' + require("../assets/graphql.svg") + '")',
          width: "70px",
          height: "70px"
        },
        {
          key: 11,
          name: "Jest",
          bg: 'url("' + require("../assets/jest.png") + '")',
          width: "70px",
          height: "70px"
        }
      ]
    };
  }
};
</script>

<style scoped>
.divHome {
  overflow: hidden;
}
.divHomePreview {
  padding: 80px 16%;
  position: relative;
  height: 100vh;
}
.divHeader {
  height: 20px;
}
.divName {
  font-size: 16px;
  font-weight: 400;
}
.divLinks {
}
.divLink {
  font-size: 14px;
  margin-left: 30px;
  cursor: pointer;
}
a {
  color: inherit;
}
.divAbout {
  position: relative;
  top: 35%;
  transform: translateY(-35%);
}
.divIntro {
  width: 60%;
  display: inline-block;
}
.mainHeading {
  font-weight: 500;
  font-size: 60px;
}
.mainLabel {
  font-size: 24px;
}
.divActionButtons {
  margin-top: 40px;
}
.divLinkedIn {
  background: #121212;
  height: 40px;
  width: 180px;
  color: #fff;
  display: inline-block;
  line-height: 38px;
  text-align: center;
  cursor: pointer;
  background: linear-gradient(73.43deg, #0077b5 -5.41%, #32a9e7 100%);
  border-radius: 2px;
  font-weight: 500;
  font-size: 16px;
}
.linkedinImg {
  background-image: url("../assets/linkedin.svg");
  background-repeat: no-repeat;
  width: 24px;
  height: 24px;
  display: inline-block;
  left: 0;
  background-position: center;
  position: relative;
  top: 5px;
  margin-right: 5px;
}
.mailID {
  font-weight: 300;
  line-height: 40px;
  font-size: 16px;
  display: inline-block;
  margin-left: 30px;
  cursor: pointer;
  color: rgba(0, 0, 0, 0.6);
  background-image: url("../assets/mail.svg");
  background-position: 0 13px;
  background-repeat: no-repeat;
  padding-left: 30px;
}
.divImage {
  width: 40%;
  background-image: url("../assets/praveen.jpg");
  background-position: center;
  background-repeat: no-repeat;
  display: inline-block;
  min-height: 320px;
}
.divSkills {
  background: #f5f5f5;
  padding-bottom: 66px;
  padding-left: 16%;
  padding-right: 16%;
  text-align: center;
}
.divSkill {
  background-repeat: no-repeat;
  background-position: center;
  display: inline-block;
  mix-blend-mode: luminosity;
  width: 215px;
  height: 90px;
  /* margin-left: 40px; */
  background-size: contain;
  margin-top: 60px;
  margin-right: 40px;
}
.mailLink {
  display: none;
}
.divMobile {
  display: none;
}
@media (max-width: 1024px) {
  .divHomePreview {
    padding: 40px 10%;
  }
  .divLinks {
    display: none;
  }
  .mailLink {
    display: block;
  }
  .divName {
    float: none;
  }
  .mailID {
    margin-left: 0;
  }
  .divHeader {
    height: 50px;
  }
  .mainLabel {
    display: none;
  }
  .divDesktop {
    display: none;
  }
  .divMobile {
    display: block;
  }
  .divImage {
    width: 200px;
    min-height: 200px;
    background-size: contain;
    background-position: center;
    margin: 0 auto;
  }
  .divIntro {
    width: 100%;
    text-align: center;
  }
  .mainHeading {
    line-height: 40px;
    margin: 0;
    margin-top: 15px;
  }
  .mailID {
    background-image: none;
    padding: 0;
    margin-top: 5px;
  }
  .divSkills {
    padding-left: 10%;
    padding-right: 10%;
  }
  .divSkill {
    margin-right: 15px;
  }
  .divActionButtons {
    margin-top: 30px;
  }
}
@media (min-width: 680px) and (max-width: 1000px) {
  .mainLabel {
    display: block;
    margin-top: 30px;
    font-size: 20px;
  }
  .divHomePreview {
    padding: 80px 15%;
  }
  .mainHeading {
    margin-top: 30px;
    font-size: 46px;
    line-height: 56px;
  }
  .divActionButtons {
    margin-top: 40px;
  }
  .mailID {
    margin-top: 20px;
  }
  .divImage {
    min-height: 240px;
    width: 240px;
  }
  .divName {
    font-size: 26px;
  }
  .mailID {
    font-size: 24px;
  }
  .divLinkedIn {
    width: 200px;
    height: 60px;
    line-height: 60px;
    font-size: 22px;
  }
  /* .divHomePreview {
    padding: 40px 10%;
  }
  .divImage {
    min-height: 260px;
    background-size: contain;
    background-position: center;
    vertical-align: middle;
  }
  .divIntro {
    vertical-align: middle;
  }
  .divAbout {
    top: 40%;
    transform: translateY(-40%);
  }
  .divSkills {
    padding-left: 10%;
    padding-right: 10%;
  } */
}
@media (min-width: 1000px) and (max-width: 1156px) {
  .mainLabel {
    display: block;
    margin-top: 30px;
    font-size: 24px;
  }
  .divHomePreview {
    padding: 100px 20%;
  }
  .mainHeading {
    margin-top: 50px;
    font-size: 60px;
    line-height: 70px;
  }
  .divActionButtons {
    margin-top: 40px;
  }
  .mailID {
    margin-top: 20px;
  }
  .divImage {
    min-height: 300px;
    width: 300px;
  }
  .divName {
    font-size: 26px;
  }
  .mailID {
    font-size: 24px;
  }
  .divImage {
    min-height: 300px;
    width: 300px;
  }
  .divLinkedIn {
    width: 200px;
    height: 60px;
    line-height: 60px;
    font-size: 22px;
  }
  /* .divHomePreview {
    padding: 40px 10%;
  }
  .divImage {
    min-height: 260px;
    background-size: contain;
    background-position: center;
    vertical-align: middle;
  }
  .divIntro {
    vertical-align: middle;
  }
  .divAbout {
    top: 40%;
    transform: translateY(-40%);
  }
  .divSkills {
    padding-left: 10%;
    padding-right: 10%;
  } */
}
@media (max-height: 900px) {
  .mainHeading {
    font-size: 40px;
    line-height: 45px;
  }
}
@media (max-height: 640px) {
  .mainHeading {
    font-size: 32px;
    line-height: 35px;
  }
}
</style>
