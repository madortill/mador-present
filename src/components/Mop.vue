<template>
  <div id="mop">
    <div
      v-for="(lomda, index) in mopData"
      :key="index"
      :id="lomda.id"
      class="lomda-card"
    >
      <img :src="lomda.src" :alt="lomda.id" class="lomda-img" :id="lomda.id" />
      <p class="lomda-title">{{ lomda.title }}</p>
      <p class="lomda-text">{{ lomda.text }}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "mop",
  components: {},
  data() {
    return {
      mopData: [
        { id: "hinuch", title: "שאלון מי אני?", text: 'פותח ל"פסטיבל מתגייסים". משחקון למלש"בים המיועדים לגיוס בחיל החינוך והנוער.', src: "./mop/hinuch.png" },
        {
          id: "kosher",
          title: "אתר כושר",
          text: "אתר מידע למדור כושר. מכיל בתוכו את כל המידע הרלוונטי על כושר ואימון גופני בקריית ההדרכה.",
          src: "./mop/kosher.png",
        },
        { id: "arrestDocuments", title: "לומדת מסמכי מעצר", text: "", src: "./mop/arrestDocuments.png" },
        { id: "learningGame", title: "משחוק בלמידה מרחוק", text: "לומדת הסבר על כלים דיגיטליים המסייעים בתכנון והעברת הדרכות או הכשרות מרחוק. פותח במהלך מלחמת עם כלביא.", src: "./mop/learningGame.png" },
        { id: "cranes", title: "לומדת עגורנים", text: 'פותח עבור קורס עגורנים בבה"ד 20. נועד להעביר את החלק התאורטי של הקורס ללמידה מרחוק.', src: "./mop/cranes.png" },
      ],
    };
  },
  methods: {
  },
};
</script>

<style scoped>
#mop {
  display: flex;
  align-items: center;
  justify-content: center;
}

.lomda-card {
  height: 30rem;
  width: 20rem;
  background-color: #f4f9e1;
  border: 5px solid #d2e4b0;
  border-radius: 20px;
  text-align: center;
  margin: 1rem;
  font-family: "carmela";
}

.lomda-img {
  margin-top: 0.5rem;
  max-width: 18rem;
  border-radius: 20px;
  margin-bottom: 0rem;
}

.lomda-title {
  margin-top: 0rem;
  font-size: 2rem;
  margin-bottom: 0.6rem;
}

.lomda-text {
  margin-top: 0.1rem;
  font-size: 1.1rem;
}
</style>
