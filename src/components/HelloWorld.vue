<template>
  <div class="hello">
  <form id="todo-field" v-on:submit="submitForm">
    <input type="text" placeholder="Search" v-model="search" />
    <div style="margin-top: 8px;"><button>Reset</button></div>
  </form>
    <div style="margin-top: 8px;" v-for="customer in filteredCustomer" :key="customer.id">
      <span>{{customer.name}}</span>        
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      search: "",
      customers: [
        {
          id: "1",
          name: "user 1 for a guide and recipes",
          email: "ab@gmail.com",
          phone: "5786965906",
          unread: "0",
        },
        {
          id: "2",
          name: "user 2 on how to configure",
          email: "abcd@gmail.com",
          phone: "576676886",
          unread: "0",
        },
        {
          id: "3",
          name: "user 3  customize this project",
          email: "test@gmail.com",
          phone: "67689696",
          unread: "0",
        },
        {
          id: "4",
          name: "user 4 check out the vue-cli documentation.",
          email: "d@gmail.com",
          phone: "576865896",
          unread: "0",
        },
      ],
    };
  },

   computed: {
    filteredCustomer() {
      return this.customers.filter((cust) => {
        return cust.name.toLowerCase().includes(this.search.toLowerCase());
      });
    },
  },

  submitForm(e){
    this.search = "";
    e.preventDefault();
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
