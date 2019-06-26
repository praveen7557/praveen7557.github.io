<template>
  <div class="divContact" id="contact">
    <h3 class="projectsMainHeading">Contact</h3>
    <p class="contactAbout">Have a project you’d like to discuss? I'd love to hear from you.</p>
    <div class="divContactForm DN">
      <div class="divContactBtn divChatStart" v-if="step==1" @click="enterClick(1)">Let's Chat</div>
      <div class="divContactBtn divChatBox" v-show="step==2">
        <input
          ref="name"
          type="text"
          placeholder="Enter name"
          v-model="name"
          class="inpField"
          v-on:keyup.enter="enterClick(2)"
        >
      </div>
      <div class="divContactBtn divChatBox" v-show="step==3">
        <input
          ref="mail"
          type="text"
          placeholder="Enter mail"
          v-model="mail"
          class="inpField"
          v-on:keyup.enter="enterClick(3)"
        >
      </div>
      <div class="divContactBox divContactBtn" v-show="step==4">
        <textarea ref="message" class="inpBox" v-model="message" rows="7"/>
        <div class="divMessageSubmit" @click="enterClick(4)">Send</div>
      </div>
      <div class="divContactBtn divSuccess" v-show="step==5">Success</div>
      <label class="errorMessage">{{error}}</label>
    </div>
    <a href="mailto:praveenb0800@gmail.com">
      <div class="mailID footerMail">praveenb0800[at]gmail.com</div>
    </a>
    <div class="socialButtons">
      <a href="https://www.linkedin.com/in/praveen-bolla-2a6356b0/">
        <div class="socialButton linkedIn"></div>
      </a>
      <a href="https://github.com/praveen7557">
        <div class="socialButton gitHub"></div>
      </a>
    </div>
  </div>
</template>

<script>
import axios from "axios";
import { API_LINK } from "../ApiLink.js";

export default {
  name: "Contact",
  data() {
    return {
      step: 1,
      name: "",
      mail: "",
      message: "",
      error: ""
    };
  },
  methods: {
    enterClick(step) {
      this.error = "";
      if (step == 1) {
        this.step++;
        setTimeout(() => {
          this.$refs.name.focus();
        }, 200);
      } else if (step == 2) {
        if (this.name.trim() != "") {
          this.error = "";
          this.step++;
          setTimeout(() => {
            this.$refs.mail.focus();
          }, 200);
        } else {
          this.error = "Please enter name";
        }
      } else if (step == 3) {
        if (this.name.trim() != "") {
          if (this.validateEmail(this.mail)) {
            this.error = "";
            this.step++;
            setTimeout(() => {
              this.$refs.message.focus();
            }, 200);
          } else {
            this.error = "Please enter a valid email";
          }
        } else {
          this.error = "Please enter mail";
        }
      } else if (step == 4) {
        if (this.message.trim() != "") {
          this.error = "";
          axios({
            method: "post",
            url: API_LINK + "send",
            data: {
              receiver: "praveenb0800@gmail.com",
              subject:
                this.name + " has contacted you on your portfolio website",
              emailBody:
                "Hi Praveen, <br/>You have a new message on your portfolio website. <br/>Details are as follows: <br/> Name: " +
                this.name +
                "<br/>mail: <a href=mailto:" +
                this.mail +
                ">" +
                this.mail +
                "</a><br/>Message: " +
                this.message +
                "<br/><br/> Regards,<br/> Your Friendly Bot."
            }
          }).then(function(response) {
            console.log(response);
          });
          this.step++;
        } else {
          this.error = "Please enter a message";
        }
      }
    },
    validateEmail(email) {
      var re = /^(([^<>()\[\]\\.,;:\s@"]+(\.[^<>()\[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/;
      return re.test(String(email).toLowerCase());
    }
  }
};
</script>

<style scoped>
.divContact {
  background-color: #f5f5f5;
  padding: 35px 16%;
  padding-bottom: 120px;
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
.contactAbout {
  font-size: 16px;
  font-weight: 400;
  width: 50%;
  margin-top: 10px;
}
.divContactForm {
  margin-top: 30px;
}
.divContactBtn {
  background: #02cd70;
  border-radius: 8px;
  width: 280px;
  height: 40px;
  font-weight: 500;
  font-size: 16px;
  color: white;
  line-height: 38px;
  position: relative;
}
.divChatStart {
  cursor: pointer;
  background-image: url("../assets/chat.svg");
  background-position: 36px;
  background-size: 18px;
  background-repeat: no-repeat;
  padding-left: 65px;
}
.divContactBtn:after {
  content: " ";
  position: absolute;
  background-repeat: no-repeat;
  background-position: right;
  width: 20px;
  height: 100%;
  right: 20px;
}
.divChatStart:after {
  background-image: url("../assets/next.svg");
}
.divChatBox:after {
  background-image: url("../assets/enter.svg");
}
.socialButtons {
  margin-top: 60px;
}
.socialButton {
  margin-right: 30px;
  height: 24px;
  width: 24px;
  display: inline-block;
}
.linkedIn {
  background-image: url("../assets/linkedin_footer.svg");
  background-repeat: no-repeat;
}
.gitHub {
  background-image: url("../assets/github.svg");
  background-repeat: no-repeat;
}
.inpField {
  height: 100%;
  width: 80%;
  background: transparent;
  padding-left: 10px;
  color: #fff;
  font-family: "Source Sans Pro", sans-serif;
  font-size: 16px;
}
.divContactBox {
  height: 160px;
  position: relative;
}
::-webkit-input-placeholder {
  /* Chrome/Opera/Safari */
  color: rgba(255, 255, 255, 0.7);
}
::-moz-placeholder {
  /* Firefox 19+ */
  color: rgba(255, 255, 255, 0.7);
}
:-ms-input-placeholder {
  /* IE 10+ */
  color: rgba(255, 255, 255, 0.7);
}
:-moz-placeholder {
  /* Firefox 18- */
  color: rgba(255, 255, 255, 0.7);
}
.inpBox {
  width: 97%;
  background: transparent;
  resize: none;
  border: none;
  outline: none;
  border-top-left-radius: 8px;
  border-top-right-radius: 8px;
  padding-top: 13px;
  padding-left: 20px;
  padding-right: 20px;
  color: #fff;
  font-family: "Source Sans Pro", sans-serif;
  font-size: 16px;
}
.divMessageSubmit {
  height: 40px;
  position: absolute;
  bottom: 0;
  width: 100%;
  background: #00c366;
  border-bottom-left-radius: 8px;
  border-bottom-right-radius: 8px;
  cursor: pointer;
  padding-left: 20px;
  font-size: 16px;
  font-weight: 500;
}
.divMessageSubmit:after {
  content: " ";
  position: absolute;
  background-repeat: no-repeat;
  background-position: right;
  width: 20px;
  height: 100%;
  right: 20px;
  background-image: url("../assets/next.svg");
}
.divSuccess {
  background-image: url("../assets/done.svg");
  background-position: 90px;
  background-size: 20px;
  background-repeat: no-repeat;
  padding-left: 120px;
}
.errorMessage {
  color: red;
  display: inline-block;
  margin-top: 15px;
  height: 18px;
  width: 100%;
}
.VH {
  visibility: hidden;
}
.footerMail {
  color: rgba(0, 0, 0, 0.6);
  font-weight: 400;
  font-size: 16px;
  margin-top: 15px;
}
@media (max-width: 576px) {
  .contactAbout {
    width: 100%;
  }
  .socialButtons {
    margin-top: 30px;
    text-align: center;
  }
  .gitHub {
    margin-right: 0;
  }
  .divContact {
    padding: 35px 10%;
    padding-bottom: 60px;
  }
}
@media (max-width: 768px) {
  .divContact {
    padding: 35px 10%;
    padding-bottom: 60px;
  }
  .contactAbout {
    width: 70%;
  }
  .socialButtons {
    margin-top: 40px;
  }
}
@media (max-height: 640px) {
  .divContactBtn {
    width: 260px;
  }
}
</style>
