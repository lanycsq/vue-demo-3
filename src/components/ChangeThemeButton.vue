<template>
    <div>
        <button @click="change">换肤</button>
        <button @click="changeFontSize('big')">大字</button>
        <button @click="changeFontSize('small')">小字</button>
        <button @click="changeFontSize('normal')">正常字</button>



    </div>
</template>

<script>
    export default {
       inject:['themeName','changeTheme','changeFontSize'],
        methods:{
           change(){
               this.changeTheme();
           }
        }
    }
</script>

<style scoped>

</style>