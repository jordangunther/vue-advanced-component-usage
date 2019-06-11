<template>
  <div class="container">
    <div class="row">
      <div class="col-xs-12">
        <br>
        <button class="btn btn-primary" @click="selectedComponent = 'appBlue'">Load Blue Template</button>
        <button class="btn btn-success" @click="selectedComponent = 'appGreen'">Load Green Template</button>
        <button class="btn btn-danger" @click="selectedComponent = 'appRed'">Load Red Template</button>
        <hr>
        <p>{{ selectedComponent }}</p>
<!--        Keep alive will maintain the state of the component when you switch to using other components. Ex switch green template to darker and it remains dark as you toggle back and forth They usually are destroyed and created. If you still want to use those hooks you can now use activated() and deactivated() instead-->
        <keep-alive>
          <component :is="selectedComponent">
            <h1 slot="blue-title">I am blue and I am sad</h1>
            <p slot="blue-subtitle">Sometimes I am chill</p>

            <h1 slot="green-title">I am green and I am jealous</h1>

            <h1 slot="red-title">I am red and I am mad</h1>
            <p>Sometimes I am passionate</p>
          </component>
        </keep-alive>
      </div>
    </div>
  </div>
</template>

<script>
  import Blue from './components/Blue.vue';
  import Green from './components/Green.vue';
  import Red from './components/Red.vue';

  export default {
    data() {
      return {
        selectedComponent: 'appRed'
      }
    },
    components: {
      appBlue: Blue,
      appGreen: Green,
      appRed: Red
    }
  }
</script>

<style>
  /*this stile is kinda like the template style and will be applied to the slot in the component you pass it too. Any styles in the component will override this one*/
  .title {
    color: white;
  }
</style>
