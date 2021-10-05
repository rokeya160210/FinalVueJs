<template>
  <div class=" container d-flex justify-content-center">

    <table class="table" border="2" border-dark>
        <thead>
    <tr>
      <th scope="col">#</th>
      <th scope="col">First Name</th>
      <th scope="col">Last Name</th>
      <th scope="col">Course</th>
    </tr>
  </thead>

      <tr v-for="item in items" :key="item.index">
          <td>{{item.index}}</td>
        <td>{{item.fname}}</td>
        <td>{{item.lname}}</td>
        <td>{{item.course}}</td>
        
      </tr>
    </table>
  </div>
</template>

<script>
const axios = require("axios").default;

export default {
  name: "Table",
  data: function () {
    return {
      items: [
        {
          index: 1,
          fname: "Rokeya ",
          lname: "Shikha",
          course: "Vue JS"
        },
        {
          index: 2,
          fname: "Hygenic",
          lname: "islam",
          course: " Bootstrap5"
        },
        {
          index: 3,
          fname: "Mr. ",
          lname: "ghosh",
          course: " CSS"
        },
        {
          index: 4,
          fname: "Rdn",
          lname: "islam",
          course: " Html"
        },
        {
          index: 5,
          fname: "C",
          lname: "D",
          course: " Reactive"
        },
      ],
      responseData: "",
    };
  },
  methods: {
    getData: function () {
      console.log('Api request is in progress.');
      let self = this;
      axios.get("http://localhost:3000/api/get-data")
        .then(function (response) {
          if(response.status == 200) {
            self.responseData = response.data;
          } else {
            self.responseData = 'Error';
          }
        })
        .catch(function (error) {
          console.log(error);
        })
        .then(function () {
          console.log('Api request done.');
        });
    },
  },
  created() {
    this.getData();
  },
};
</script>

<style scoped>
</style>
