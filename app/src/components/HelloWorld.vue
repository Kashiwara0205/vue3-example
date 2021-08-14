<template>
  <div class="hello">
    {{ getMsg }}
    <br>
    <input v-model="color" placeholder="edit me">
    <button v-on:click="onClick">Click me</button>
  </div>
</template>

<script>
import { defineComponent, computed, ref } from "vue";

export default defineComponent({
  props: {
    msg:{
      type: String,
      required: true
    }
  },
  setup(props){
    const getMsg = computed(() => props.msg)

    const color = ref("red")

    const onClick = ()=>{
      console.log("click!")
      console.log(color.value)
    }

    return{
      getMsg,
      color,
      onClick
    }
  }
})
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
