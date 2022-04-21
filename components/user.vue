<template>
  <div class="m-10">
    <div>Test</div>
    <!-- {{ users }} -->

    <div
      v-for="user in users"
      :key="user.index"
      class="
        px-7
        py-3
        hover:shadow-2xl
        shadow-md
        bg-red-100
        mb-3
        rounded-md
        lg:hidden
      "
    >
      <div>{{ user.name }}</div>
      <div>{{ user.email }}</div>
      <div>{{ user.phone }}</div>
      <div></div>
    </div>
  </div>
</template>

<script>
import axios from "axios";
export default {
  data() {
    return {
      users: [],
    };
  },
  mounted() {
    this.getUser();
  },
  methods: {
    async getUser() {
      const users = await axios.get(
        "https://jsonplaceholder.typicode.com/users"
      );
      this.users = users.data;
      console.log("user", this.users);
    },
  },
};
</script>

<style lang="scss" scoped>
</style>