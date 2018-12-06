<template>
  <div id="app">
    <h1>{{title}}</h1>
    <!-- import form helper -->
    <!-- pass in unique info from parent component to fill slots -->
    <!-- <form-helper v-bind:title="title">
      <div slot="form-header">
        <h3>Form Title</h3>
        <p>Form info</p>
      </div>
      <div slot="form-fields">
        <input type="text" placeholder="username" required />
        <input type="text" placeholder="password" required />
      </div>
      <div slot="form-controls">
        <button v-on:click="handleSubmit">Submit</button>
      </div>
    </form-helper> -->

  <!-- keeps everything that is input on either form intact even if we switch forms -->
  <keep-alive>
    <!-- renders whatever component we set "is" to -->
    <component v-bind:is="component"></component>
  </keep-alive>
  <!-- buttons to toggle form that is seen, dynamic property from data -->
  <button v-on:click="component = 'form-one'">Show Form One</button>
  <button v-on:click="component = 'form-two'">Show Form Two</button>
  </div>
</template>

<script>
// import FormHelper from './components/FormHelper.vue';
import FormOne from './components/FormOne.vue';
import FormTwo from './components/FormTwo.vue';

export default {
  components: {
    // 'form-helper': FormHelper,
    'form-one': FormOne,
    'form-two': FormTwo
  },
  data () {
    return {
      title: 'I am a dynamic slot title',
      component: 'form-one'
    }
  }
}
</script>

<style>

</style>
