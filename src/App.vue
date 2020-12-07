<template>
  <p>xxxxxxx</p>
  <button v-for="(item,index) in studentArr" :key="index" @click="selectStuFn(index)">
    {{index}}:{{item}}
  </button>
  <hr/>
  <span>请 {{selectPeople}} 同学来回答问题</span>

</template>

<script lang='ts'>
  import {defineComponent,ref} from 'vue';
  export default defineComponent({
    name:"APP",
    setup(){
      const studentArr = ref(['张三','李四','王五']);
      const selectPeople = ref("");
      const selectStuFn = (index:number)=>{
        selectPeople.value = studentArr.value[index];
      };
      return {studentArr,selectPeople,selectStuFn};
    },
  });
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
</style>
