<template>
  <div class="home">
    <button v-on:click="firstButton()">Click me!</button>
    <br />
    <button v-if="secondShow" v-on:click="secondButton()">Don't click this button</button>
  </div>
</template>

<script>
// @ is an alias to /src
import Swal from "sweetalert2";
export default {
  data: function() {
    return {
      secondShow: false,
    };
  },
  created: function() {
    Swal.fire("Welcome!", "Please press the button!");
  },
  methods: {
    firstButton: function() {
      Swal.fire("Congrats, you pressed the button!", "Don't click the next one, though.", "success");
      this.secondShow = true;
    },
    secondButton: function() {
      Swal.fire("Wow, rude!", "I said not to do it! I could not have been more clear!", "error");
    },
  },
};
</script>
