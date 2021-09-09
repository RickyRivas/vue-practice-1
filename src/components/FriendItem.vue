<template>
  <li>
    <h2>{{ name }}</h2>
    <p class="age">{{ age }}</p>
    <p>{{ car }}</p>
    <p>{{ id }}</p>
    <base-button @click='removeFriend'>Delete</base-button>
  </li>
</template>
<script>
export default {
  inject: ["removeFriend"],
  props: ["name", "age", "car", "id"],
  data() {
    return {};
  },
};
</script>
<style scoped>
li {
  box-shadow: rgba(100, 100, 111, 0.2) 0px 7px 29px 0px;
  width: 100%;
  max-width: max-content;
  display: flex;
  justify-content: space-around;
  align-items: center;
  padding: 1em;
  border-radius: 1em;
}
li h2 {
  margin-right: 1em;
}
li p {
  margin-right: 1em;
}
.age {
  border: 1px solid red;
  border-radius: 50%;
  padding: 10px 12px;
}
</style>