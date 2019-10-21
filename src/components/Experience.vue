<template>
  <div class="divExperience">
    <h3 class="projectsMainHeading">Experience</h3>
    <div class="divExpBlock">
      <div class="expBlock" v-for="item in experience" :key="item.key">
        <div class="leftBlock block">
          <div class="divPosition">{{item.position}}</div>
        </div>
        <div class="middleBlock block">
          <div class="exp">
            {{item.experience}}
            <label class="expLabel">{{item.expLabel}}</label>
          </div>
        </div>
        <div class="rightBlock block">
          <div class="divDuration">{{item.duration}}</div>
          <div class="divCompany">{{item.company}}</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Experience",
  data() {
    return {
      experience: [
        {
          key: 4,
          position: "Senior Software Development Engineer",
          experience: "9",
          expLabel: "Months",
          duration: "Jan 2019 - Present",
          company: "West Agile Labs"
        },
        {
          key: 1,
          position: "Full-stack Developer",
          experience: "1",
          expLabel: "Year",
          duration: "Mar 2018 - Mar 2019",
          company: "Baseblock IT Solutions"
        },
        {
          key: 2,
          position: "Software Engineer",
          experience: "3",
          expLabel: "Years",
          duration: "Jun 2015 - Mar 2018",
          company: "Analytics Quotient"
        },
        {
          key: 3,
          position: "Graduation, B.Tech(ECE)",
          experience: "4",
          expLabel: "Years",
          duration: "Jul 2011 - May 2015",
          company: "IIT Dhanbad"
        }
      ]
    };
  }
};
</script>

<style scoped>
.divExperience {
  padding: 40px 16%;
  padding-bottom: 80px;
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
  width: 250px;
}
.divExpBlock {
  margin-top: 60px;
  position: relative;
}
.expBlock {
  margin-bottom: 100px;
}
.block {
  vertical-align: middle;
  display: inline-block;
}
.leftBlock {
  width: 40%;
}
.middleBlock {
  width: 20%;
  /* text-align: center; */
  padding-left: 5.5%;
  position: relative;
}
.rightBlock {
  width: 40%;
}
.divPosition {
  font-size: 24px;
  text-transform: uppercase;
}
.exp {
  font-size: 40px;
}
.expLabel {
  font-weight: 900;
  text-transform: uppercase;
  color: rgba(0, 0, 0, 0.1);
  font-size: 40px;
  margin-left: -5px;
}
.divDuration {
  font-size: 16px;
  text-align: right;
  text-transform: uppercase;
}
.divCompany {
  font-size: 14px;
  text-align: right;
  text-transform: uppercase;
  margin-top: 10px;
}
.middleBlock::before {
  content: " ";
  position: absolute;
  top: 100%;
  left: 32%;
  width: 0px;
  height: 105px;
  border: 0.5px solid rgba(0, 0, 0, 0.1);
}
div.expBlock:last-child .middleBlock::before {
  display: none;
}
@media (max-width: 576px) {
  .divExperience {
    padding: 40px 20px;
  }
  .divExpBlock {
    margin-top: 40px;
  }
  .block {
    width: 100% !important;
    margin-bottom: 15px;
  }
  .middleBlock {
    text-align: center;
    padding: 0;
  }
  .middleBlock::before {
    height: 125px;
    left: 50%;
  }
  .expBlock {
    margin-bottom: 70px;
  }
  .divPosition {
    font-size: 20px;
    font-weight: 400;
  }
  .divDuration {
    font-size: 14px;
  }
  .divCompany {
    font-size: 12px;
  }
}
</style>
