<template>
  <div class="container">
    <Form v-on:formInput="handleFormInput" v-on:formSubmit="handleFormSubmit" />
    <Sheet :sheetData="formData" :matchingList="matchingList" />
  </div>
</template>

<script>
import Form from "./components/Form";
import Sheet from "./components/Sheet";
export default {
  name: "App",
  components: {
    Form,
    Sheet,
  },
  data() {
    return { formData: {}, matchingList: [] };
  },
  methods: {
    handleFormInput: function(formData) {
      this.formData = formData;
    },
    handleFormSubmit: function(formData) {
      this.matchingList.push(formData);
      this.formData = {};
      console.log(this.matchingList)
      console.log(this.formData)
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.container {
  display: flex;
  justify-content: space-between;
  max-width: 1200px;
  margin: 0 auto;
}
</style>
