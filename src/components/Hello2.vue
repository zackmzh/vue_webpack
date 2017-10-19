<template>
  <div class="hello2 container">
    <label class="mt-2">Please Enter Your Text</label>
    <div class="input-group mb-5">
      <input type="text" class="form-control" placeholder="Enter the Text" v-model="message">
      <span class="input-group-btn">
        <button class="btn btn-primary" type="button" @click="submit()">Go!</button>
      </span>
    </div>

    <div class="media my-4" v-for="item in messages">
      <img v-if="item.username != username" class="d-flex align-self-start mr-3" src="http://lorempixel.com/100/100/" alt="Generic placeholder image">
      <div class="media-body">
        <h5 class="mt-0">{{ item.username }}</h5>
        <p>{{ item.message }}</p>
      </div>
      <img v-if="item.username == username" class="d-flex ml-3" src="http://lorempixel.com/100/100/sports/" alt="Generic placeholder image">
    </div>

    <!--<div class="media">-->
      <!--<div class="media-body">-->
        <!--<h5 class="mt-0 mb-1">Media object</h5>-->
        <!--Cras sit amet nibh libero, in gravida nulla. Nulla vel metus scelerisque ante sollicitudin. Cras purus odio, vestibulum in vulputate at, tempus viverra turpis. Fusce condimentum nunc ac nisi vulputate fringilla. Donec lacinia congue felis in faucibus.-->
      <!--</div>-->
      <!--<img class="d-flex ml-3" src="http://lorempixel.com/100/100/sports/" alt="Generic placeholder image">-->
    <!--</div>-->
  </div>
</template>

<script>
  export default {
    name: 'hello2',
    data () {
      return {
        msg: 'Welcome to Your Vue.js App',
        username: 'Rick',
        message: '',
        messages: [
          {
            username: 'Rico',
            message: 'Hello'
          },
          {
            username: 'Rick',
            message: 'You too'
          }
        ]
      }
    },
    methods: {
      submit () {
        let that = this
        that.messages.push({
          username: that.username,
          message: that.message
        })
      }
    }
  }
</script>

<style scoped>

</style>

