<template>
  <form ref="form" >
    <input type="text" name="Word" v-model="word"  @change="handleChange" />
      <br />
    <textarea type="text" name="Definition" v-model="definition"  @change="handleChange"  />
      <button type="submit" name="submit" v-on:click="submit">Submit</button>
  </form>

</template>

<script>
export default {
  name: "Form",
  data()  {
    return {

      word: "",
      definition: "",
    };
  },
  methods: {
    handleChange: function() { 
        this.$emit('formInput',{ word: this.word, definition: this.definition})
    },
    submit: function(e) {
        e.preventDefault()
       this.$emit('formSubmit',{ word: this.word, definition: this.definition})
        this.word = ""
       this.definition = ""
    }
    }
};
</script>

<style></style>
