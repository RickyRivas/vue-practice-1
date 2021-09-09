<template>
  <h2>Rickys Vue Practice</h2>
  <div>
    <base-button @click="componentSelected('friends-list')"
      >View Friends</base-button
    >
    <base-button @click="componentSelected('add-friend')"
      >Add New Friend</base-button
    >
  </div>
  <component :is="componentIsSelected"></component>
</template>

<script>
import FriendsList from "./components/FriendsList.vue";
import AddFriend from "./components/AddFriend.vue";

export default {
  name: "App",
  components: { FriendsList, AddFriend },
  data() {
    return {
      componentIsSelected: "friends-list",
      friends: [
        {
          id: "1",
          name: "Ariel",
          age: 22,
          car: "BMW",
        },
        {
          id: "2",
          name: "Gama",
          age: 21,
          car: "Toyota",
        },
      ],
    };
  },
  provide() {
    return {
      friends: this.friends,
      removeFriend: this.removeFriend,
      componentIsSelected: this.componentIsSelected
    };
  },
  methods: {
    componentSelected(tab) {
      this.componentIsSelected = tab;
    },
    removeFriend(friendID) {
      const friendI = this.friends.findIndex(friend => friend.id === friendID);
      this.friends.splice(friendI);
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
