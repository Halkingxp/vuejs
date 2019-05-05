<template>
    <div class="testclass">
        this is {{testData}}
    </div>    
</template>

<script>
export default {
    data(){
        return {

        }
    },
    props:{
        testData:String,
    },
    created(){
        // this.testData = "change testData data"
        this.$emit("update:testData","change testData data");
    }

}
</script>

<style scoped>

</style>


