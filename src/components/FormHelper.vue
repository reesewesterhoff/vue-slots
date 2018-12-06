<template>
  <div>
      <!-- create slots for things like forms so that any time there is a form -->
      <!-- you can insert different info into the pre made areas -->
      <h1>Please fill out our form...</h1>
      <h2>{{title}}</h2>
      <form>
          <div id="form-header">
              <slot name="form-header"></slot>
          </div>
          <div id="form-fields">
              <slot name="form-fields"></slot>
          </div>
          <div id="form-controls">
              <slot name="form-controls"></slot>
          </div>
          <div id="useful-links">
              <ul>
                  <li><a href="#">Link 1</a></li>
                  <li><a href="#">Link 2</a></li>
                  <li><a href="#">Link 3</a></li>
                  <li><a href="#">Link 4</a></li>
              </ul>
          </div>
      </form>
  </div>
</template>

<script>
export default {
    props: {
        title: {
            type: String
        }
    },
  data () {
    return {
      
    }
  }
}
</script>

<style scoped>
h1, h2{
    text-align: center;
}
form{
    width: 100%;
    max-width: 960px;
    margin: 0 auto;
}
#useful-links ul{
    padding: 0;
}
#useful-links li{
    display: inline-block;
    margin-right: 10px;
}
form > div{
    padding: 20px;
    background: #eee;
    margin: 20px 0;
}
#form-header{
    background: #ddd;
    border: 1px solid #bbb;
}
</style>
