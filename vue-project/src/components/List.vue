<template>
  <div class="main">
    <table class=" border-table table table-striped">
  <thead>
    <tr >
        <!-- <th scope="col" class="th-border">#</th> -->
        <th scope="col" class="th">ID</th>
        <th scope="col" class="th">Name</th>
        <th scope="col" class="th">Age</th>
        <th scope="col" class="th">Phone</th>
        <th scope="col" class="th">Email</th>

    </tr>
  </thead>
  <tbody>
            <tr class="tr-items" v-for="element in list" v-bind:key="element.ID">
        <!-- Тут массив в массиве, можно конечно и поизящней сделать, но т.к. всего 5 элементов, прописал руками -->
        <th scope="row" class="th">{{ element[0].value }}</th>
        <th scope="row" class="th">{{ element[1].value }}</th>
        <th scope="row" class="th">{{ element[2].value }}</th>
        <th scope="row" class="th">{{ element[3].value }}</th>
        <th scope="row" class="th">{{ element[4].value }}</th>
        <button type="button" class="btn btn-warning">Delete</button>
        <button type="button" class="btn btn-success">Update</button>
      </tr>

  </tbody>
</table>


  </div>
</template>
<script>
import Vue from "vue";
import axios from "axios";
import VueAxios from "vue-axios";

Vue.use(VueAxios, axios);
export default {
  name: "List",
  data() {
    return { list: undefined };
  },
  mounted() {
    Vue.axios.get("https://frontend-test.netbox.ru").then(resp => {
      // return  console.log(resp.data);
      this.list = resp.data;
    });
  }
};
</script>
<style scoped>
.border-table {
  margin: 100px 20px 0px 50px;
  }
/* .tr-border {
  min-width: 100px;
} */
.td {
  font-size: 20px;
  font-family: "Franklin Gothic Medium", "Arial Narrow", Arial, sans-serif;
  border: 2px solid orange;
  padding: 15px;
}
.tr-items{
  align-items: center;
}
.btn {
  margin: 10px;
  padding: 20px;
}
</style>
