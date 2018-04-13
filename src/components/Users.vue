<template>
  <div class="Users">
    <h1>Users</h1>
    <div v-for="user in users" class="row">
      <div class="col fill">
        <span :class="{ active: user.active }">{{user.name}}  {{user.email}}</span>
      </div>
      <div class="col s1">
        <input type="checkbox" v-model="user.active">
      </div>
      <div class="col s1">
        <button v-on:click="deleteUser(user)">X</button>
      </div>
      
    </div>

    <div class="margin15"></div>
    <div class="margin15"></div>

    <form v-on:submit="addUser">
    <div class="row">
      <label class="col m4">
        Name:        
      </label>
      <input class="col fill" type="text" v-model="newUser.name" placeholder="Insert name" />
    </div>
    <div class="margin15"></div>
    <div class="row">
      <label class="col m4">
        Email:        
      </label>
      <input class="col fill" type="text" v-model="newUser.email" placeholder="Insert email" />
    </div>
    <div class="margin15"></div>
    <div class="row">
      <button class="col" type="submit">Add</button>
    </div>
    </form>
  </div>
</template>

<script>
  export default {
    name: 'users',
    data: () => {
      return {
        users: [
          {
            name: 'User 1',
            email: 'user1@a.com',
            active: true
          },
          {
            name: 'User 2',
            email: 'user2@a.com',
            active: false
          },
          {
            name: 'User 3',
            email: 'user3@a.com',
            active: false
          },
          {
            name: 'User 4',
            email: 'user4@a.com',
            active: true
          }
        ],
        newUser: {
          name: '',
          email: '',
          active: false
        }
      }
    },
    methods: {
      addUser: function (e) {
        this.users.push(this.newUser)
        this.newUser = {
          name: '',
          email: '',
          active: false
        }
      },
      deleteUser: function (user) {
        this.users.splice(this.users.indexOf(user), 1)
      }
    }
  }
</script>

<style scoped>
  .active {
    text-decoration: line-through;
  }

  .margin15 {
    margin-top: 15px;
  }
</style>