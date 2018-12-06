<template>
  <div id="app">
    <h1>{{title}}</h1>
    <!-- import form helper -->
    <!-- pass in unique info from parent component to fill slots -->
    <form-helper v-bind:title="title">
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
    </form-helper>
  </div>
</template>

<script>
import FormHelper from './components/FormHelper.vue';

export default {
  components: {
    'form-helper': FormHelper,
  },
  data () {
    return {
      title: 'I am a dynamic slot title'
    }
  }
}
</script>

<style>

</style>
