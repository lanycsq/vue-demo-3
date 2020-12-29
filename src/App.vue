<template>
  <div :class="`app theme-${themeName} fontSize-${fontSizeName}`">
    <Child1/>
    <button>x</button>
    <Child2/>
    <button>x</button>
    <Child3/>
    <button>x</button>
    <Child4/>
    <button>x</button>
    <Child5/>
    <button>x</button>
  </div>
</template>

<script>
  import Child1 from "./components/Child1.vue";
  import Child2 from "./components/Child2.vue";
  import Child3 from "./components/Child3.vue";
  import Child4 from "./components/Child4.vue";
  import Child5 from "./components/Child5.vue";
  export default {
    name: "App",
    provide(){
      return{
        themeName: this.themeName,
        changeTheme:this.changeTheme,
        changeFontSize:this.changeFontSize
      }
    },
    data() {
      return {
        themeName: "blue", // 'red'
        fontSizeName: "normal" ,// 'big' | 'small'
      };
    },
    components: {
      Child1,
      Child2,
      Child3,
      Child4,
      Child5
    },
    methods:{
      changeTheme(){
        if(this.themeName==="blue"){
          this.themeName='red'
        }else {
          this.themeName='blue'
        }
      },
      changeFontSize(name){
        // if(name==='normal'||name==='big'||name==='small'){
        //   this.fontSizeName=name;
        // }
        if(['normal','big','small'].indexOf(name)>=0){
          this.fontSizeName=name;
        }
      }
    }
  };
</script>

<style>
  .app {
    font-family: "Avenir", Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
  }
  .app button{
    border:none;
    outline: none;
    border-radius: 2px;
    padding: 2px 5px;
    margin: 5px 10px 5px 0;
    font-size: inherit;
    /*line-height: 10px;*/
  }
  .app.theme-blue button {
    background: blue;
    color: white;
  }
  .app.theme-blue {
    color: darkblue;
  }

  .app.theme-red button {
    background: red;
    color: white;
  }
  .app.theme-red {
    color: darkred;
  }
  .app.fontSize-big{
    font-size: 20px;
  }
  .app.fontSize-small{
  font-size: 12px;
  }
  .app.fontSize-normal{
  font-size: 16px;
  }
</style>
