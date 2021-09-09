<template>
  <h2>Add New Friend!</h2>
  <form @submit.prevent="addNewFriend">
    <div>
      <label>Enter Name</label>
      <input type="text" v-model="enteredName" ref="enteredName" />
    </div>
    <div>
      <label>Enter Age</label>
      <input type="text" v-model="enteredAge" ref="enteredAge" />
    </div>
    <div>
      <label>Enter the car they drive</label>
      <input type="text" v-model="enteredCar" ref="enteredCar" />
    </div>
    <base-button>Submit New Data</base-button>
  </form>
</template>
<script>
export default {
  inject: ["friends", "componentIsSelected"],
  data() {
    return {};
  },
  methods: {
    addNewFriend(enteredName, enteredAge, enteredCar) {
      enteredName = this.$refs.enteredName.value;
      enteredAge = this.$refs.enteredAge.value;
      enteredCar = this.$refs.enteredCar.value;
      const friendAdded = {
        id: Math.floor(Math.random() * 10) + 1,
        name: enteredName,
        age: enteredAge,
        car: enteredCar,
      };
      this.friends.push(friendAdded);
    },
  },
};
</script>
<style scoped>
div {
  margin-bottom: 1em;
}
</style>