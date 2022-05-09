<script>
import HelloWorld from './components/HelloWorld.vue'
import TheWelcome from './components/TheWelcome.vue'
import Test from './components/Test.vue';
import Practice1 from './components/Practice1.vue';
import Practice2 from './components/Practice2.vue';
import Practice3 from './components/Practice3.vue';
import AlertMessage from './components/AlertMessage.vue';

export default{
  components:{
    Test,
    Practice1,
    Practice2,
    Practice3,
    AlertMessage
  },
  data() {
    return {
      employeeSelected:{},
      isShow:false,
      tabs:['Practice 1','Practice 2','Practice 3'],
      currentTab:'Practice 1'
    }
  },
  methods:{
    employeeDetail(employee){
      this.employeeSelected=employee;
    }
  }
}
</script>

<template>
  <header>
    <img alt="Vue logo" class="logo" src="./assets/logo.svg" width="125" height="125" />

    <div class="wrapper">
      <Test ref="test" :employeeSelected="employeeSelected"/>
      <Practice1></Practice1>
      <Practice2></Practice2>
      <Practice3 @employee-detail="employeeDetail"></Practice3>      
    </div>
  </header>

  <!-- <main>
    <TheWelcome />
  </main> -->
</template>

<style>
@import './assets/base.css';

#app {
  max-width: 1280px;
  margin: 0 auto;
  padding: 2rem;

  font-weight: normal;
}

header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

a,
.green {
  text-decoration: none;
  color: hsla(160, 100%, 37%, 1);
  transition: 0.4s;
}

@media (hover: hover) {
  a:hover {
    background-color: hsla(160, 100%, 37%, 0.2);
  }
}

@media (min-width: 1024px) {
  body {
    display: flex;
    place-items: center;
  }

  #app {
    display: grid;
    grid-template-columns: 1fr 1fr;
    padding: 0 2rem;
  }

  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }

  .logo {
    margin: 0 2rem 0 0;
  }
}
</style>
