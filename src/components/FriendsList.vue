<template>
  <div class="friend-div">
    <h1>My Friends</h1>
    <ul v-for="friend of friends" :key="friend">
      <friend-item
        :id='friend.id'
        :name="friend.name"
        :age="friend.age"
        :car="friend.car"
      ></friend-item>
    </ul>
  </div>
</template>
<script>
import FriendItem from "./FriendItem.vue";
export default {
  inject: ["friends"],
  components: { FriendItem },
  data() {
    return {};
  },
};
</script>
<style scoped>
</style>