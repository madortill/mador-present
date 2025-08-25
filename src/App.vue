<template>
  <div id="app">
    <div class="header">
      <img class="til" src="/src/assets/general/til.svg" alt="til" />
      <img
        class="mifkada"
        src="/src/assets/general/mifkada.svg"
        alt="mifkada"
      />
      <about v-if="page == 'main'"></about>
      <img v-if="page !== 'main'" @click="toMain" class="back-btn" src="/src/assets/general/back-btn.svg" alt="back-btn">
      <p class="main-title">{{ title }}</p>
      <p class="second-title" v-if="page == 'main'">רבעון ג 2025</p>
    </div>
    <div class="main-content">
      <p v-if="page !== 'main'" class="explain">{{ text }}</p>
      <fields v-if="page == 'main'" @click="toField"></fields>
      <mop v-if="page == 'mop'"></mop>
    </div>
  </div>
</template>

<script>
import About from "@/components/About.vue";
import Fields from "@/components/Fields.vue";
import Mop from '@/components/Mop.vue';
export default {
  name: "app",
  components: {
    About,
    Fields,
    Mop
  },
  
  data() {
    return {
      showAbout: false,
      title: "תוצרי מדור טיל",
      text: "",
      page: 'main',
      fieldData: {
        social: {
          title: "תחום סושיאל",
          text: "צפו בסרטוני הסושיאל שהפצנו ברשתות החברתיות"
        },
        mop: {
          title: 'תחום מו"פ',
          text: 'מפתחות הלומדה פיתחו והשיקו מספר לומדות לבה”דים ברבעון האחרון'
        },
        graphics: {
          title: "תחום גרפיקה",
          text: "ברבעון האחרון עבדנו על מספר רב של גרפיקות כאן מוצגות חלקן"
        },
        images: {
          title: "תחום וידאו - תמונות",
          text: "הצלמים שלנו תיעדו אירועים רבים כאן מוצגות חלק מהתמונות"
        },
        videos: {
          title: "תחום וידאו",
          text: "מוזמנים לצפות בסרטונים עליהם עבדנו ברבעון האחרון"
        }
      }
    };
  },
  methods: {
    toField(event) {
      this.page = event.target.id;
      this.title = this.fieldData[event.target.id].title;
      this.text = this.fieldData[event.target.id].text;
    },
    toMain() {
      this.page ='main';
      this.title = "תוצרי מדור טיל";
    }
  },
};
</script>

<style scoped>
.header {
  width: 100%;
  height: 13rem;
  background-color: #d2e4b0;
  position: absolute;
  top: 0rem;
  right: 0rem;
}

html {
  font-size: calc(10px + 0.5vw);
  margin: 0;
}

#app {
  font-family: "aharoni";
  height: 100vh;
  width: 100vw;
  background-color: #0e5648;
  position: absolute;
  top: 0rem;
  right: 0rem;
  color: #0e5648;
}

.til {
  position: absolute;
  height: 9rem;
  top: 1.5rem;
  right: 2rem;
}

.mifkada {
  position: absolute;
  height: 5rem;
  top: 1rem;
  left: 1rem;
}

.main-title {
  text-align: center;
  position: relative;
  bottom: 1 rem;
  font-size: 5rem;
  pointer-events: none;
}

.second-title {
  text-align: center;
  position: relative;
  bottom: 5rem;
  font-size: 2rem;
  font-family: "carmela";
}

.main-content {
  position: relative;
  top: 16rem;
}

.explain {
  position: relative;
  color: #F4F9E1;
  font-family: "carmela";
  text-align: center;
  font-size: 2rem;
  bottom: 1rem;
  z-index: 5;
}

.back-btn {
  position: absolute;
  top: 6rem;
  left: 5rem;
  height: 3.5rem;
  width: 3.5rem;
  padding: 0.3rem;
  border-radius: 200px;
  background-color: #0e5648;
  font-size: 2.5rem;
  cursor: pointer;
}

.back-btn:hover {
  padding: 0.7rem;
}

.back-btn:active {
  background-color: #267565;
}

@font-face {
  font-family: aharoni;
  src: url("/src/assets/fonts/._aharoniclm-bold-webfont.ttf");
}

@font-face {
  font-family: carmela;
  src: url("/src/assets/fonts/carmela.ttf");
}
</style>
