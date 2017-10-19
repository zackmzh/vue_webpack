<template>
  <div class="hello2 container">
    <label class="mt-2">Please Enter Your Text</label>
    <div class="input-group mb-5">
      <input type="text" class="form-control" placeholder="Enter the Text" v-model="message">
      <span class="input-group-btn">
        <button class="btn btn-primary" type="button" @click="submit">Go!</button>
      </span>

      <button class="btn btn-danger" @click="clearMessage">Clear screen</button>
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

    <div class="mouseTracker mt-5 mb-20" @mousemove="showXY($event)">
      {{x}},{{y}}
    </div>
  </div>

</template>

<script>
  export default {
    name: 'hello2',
    data () {
      return {
        msg: 'Welcome to Your Vue.js App',
        username: 'Rick',
        x: 0,
        y: 0,
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
        let that = this;
        that.messages.unshift({
          username: that.username,
          message: that.message
        })
        that.message = '';
      },
      clearMessage () {

          this.messages = [];
      },
      showXY (event) {
          this.x = event.offsetX;
          this.y = event.offsetY;
      }
    }
  }
</script>

<style scoped>

  .hello2 {
    height: 1000px;
  }

  .mouseTracker {
    width: 600px;
    height: 500px;
    padding: 200px 20px;
    text-align: center;
    border: 1px solid black;
  }
</style>

