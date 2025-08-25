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
        { id: "matanDam", title: "", text: "", src: "" },
        {
          id: "kosher",
          title: "לומדת כושר",
          text: "מפקדה, הסבר הסבר הסבר הסבר",
          src: "",
        },
        { id: "arrestDocuments", title: "", text: "", src: "" },
        { id: "aguranim", title: "", text: "", src: "" },
      ],
    };
  },
  methods: {
    getCloudImage(num) {
      // Determine the base URL (for local and production)
      const basePath = process.env.NODE_ENV === "production" ? "/LomdatCranes/" : "/";
      return `${basePath}media/clouds/cloud${num}.png`;  // Static path to the images in the public folder
    }
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

.lomda-title {
    font-size: 2rem;
    margin-bottom: 0.6rem;
}

.lomda-text {
    margin-top: 0.1rem;
    font-size: 1.1rem;
}
</style>
