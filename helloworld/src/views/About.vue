<template>
  <div class="about">
    <h1>This is an about page</h1>
    <Test :testData.sync="testDataA"></Test>
  </div>
</template>

<script>
import Test from "@/components/Test.vue"
export default {
  data(){
    return{
      testDataA:"About Data1",
    }
  },
  components:{
    Test,
  },
  created(){
    setTimeout(()=>{
      console.log(this.testDataA);
    },2000);
  },
}
</script>

