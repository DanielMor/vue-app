<template>
  <div class="Test">
    <h1>{{title}}</h1>
    <h2>{{message}}</h2>
    <input type="text" v-model="title">
    <div v-if="showUser">
      <p>User: </p>
      <p v-text="user.name"></p>
    </div>
    <div v-else>Nobody</div>

    <ul>
      <li v-for="item in items">{{item.title}}</li>
    </ul>
    <label>UserName: <input type="test" v-model="user.name" /></label>
    
    <button v-on:click="click()">Click me</button>
  </div>
</template>

<script>
  export default {
    name: 'test',
    props: {
      message: {
        type: String,
        default: 'Default Message'
      }
    },
    data () {
      return {
        title: 'HI',
        user: {
          name: 'John Doe'
        },
        showUser: true,
        items: [
          {
            title: 'Page 1'
          },
          {
            title: 'Page 2'
          },
          {
            title: 'Page 3'
          }
        ]
      }
    },
    methods: {
      click: function () {
        alert('HIIII')
      }
    }
  }
</script>