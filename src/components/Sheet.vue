<template>
  <div>
    <p>Match the word on the left side to its definition on the right side.</p>
    <div
      class="matchingBox"
      v-for="(item,index) in matchingList"
      :key="item.word + item.definition"
    >
  
      <h5>  <span>{{index}}. </span> {{ item.word }}</h5>
       <span class="line"></span>
      <p>{{ item.definition }}</p>
    </div>

    <div class="matchingBox">
      <h5><span>{{matchingList.length }}. </span>{{ sheetData.word }}</h5>
      <span class="line"></span>
      <p>{{ sheetData.definition }}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "Sheet",
  props: ["sheetData", "matchingList"],
};
</script>

<style>
.matchingBox {
  display: flex;
  justify-content: space-between; 
  align-items:center;
  

}
.line {
    flex-grow:1;
    background:lightgrey;
    height:3px;
    margin:0 20px;
}
</style>
