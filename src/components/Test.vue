<template lang="html">
  <div class="test">
    <input type="text" v-model="title"></br>
    <h1>{{title}}</h1>
    <h1>{{user.firstName}}</h1>
    <h1 v-if="showName">{{user.lastName}}</h1>
    <p v-else>Nobody</p>
    <ul>
      <li v-for="item in items">{{item.title}}</li>
    </ul>
    <button v-on:click="methods.greet('Hello Gurl')">Say Greeting</button>
    <input type="text" v-on:keyup="methods.pressKey" v-on:keyup.enter="methods.enterHit">
    <hr>
    <label>First Name: </label><input type="text" v-model="user.firstName">
    <br>
    <label>Last Name: </label><input type="text" v-model="user.lastName">
    <h3>{{fullName()}}</h3>
    <h2>{{msg}}</h2>
  </div>
</template>

<script>
export default {
  name: "Test",
  props: {
    msg: {
      type: String,
      default: "FooBar"
    }
  },
  data() {
    return {
      title: 'Hello World',
      user: {
        firstName: 'John',
        lastName: 'Doe'
      },
      showName: true,
      items: [
        {title: 'Item One'},
        {title: 'Item Two'},
        {title: 'Item Three'}
      ],
      methods: {
        greet: function(string){
          alert(string);
        },
        pressKey: function(e){
          console.log(e.target.value)
        },
        enterHit: function(){
          console.log("You Hit Enter")
        }
      },
      fullName: function() {
        return this.user.firstName + " " + this.user.lastName;
      }
    }
  }
}
</script>

<style scoped lang="css">

</style>
