<template>
  <!-- Navbar -->
  <!-- As a heading -->
  <div class="container">
    <nav class="navbar navbar-light bg-grey">
      <span class="navbar-brand mb-0 h1"
        >
        Buypowers.ng
        <hr />
      </span>
    </nav>
  </div>

  <!-- Page content -->
  <div class="container pb-1">
    <div class="col-4">
      
      <ul>
        <li class="badge badge-pill badge-success text-primary">
          <router-link to="/buy-electricity">Buy Electricity </router-link>
        </li>
       
        <li class="badge badge-pill badge-success text-primary">
          <router-link to="/">Transactions</router-link>
        </li>
        <li class="badge badge-pill badge-success text-primary">
          <router-link to="/">Meters</router-link>
        </li>
        <li class="badge badge-pill badge-success text-primary">
          <router-link to="/">Cards</router-link>
        </li>
        <li class="badge badge-pill badge-success text-primary">
          <router-link to="/">Logout</router-link>
        </li>
      </ul>
    
    </div>

    <div class="col-7">
      <router-view></router-view>
    </div>
  </div>
</template>
<script>
export default {
  name: "dash-layout",
  
  props: {
    title: {
      type: String,
      default: "Dashbaord",
      description: "Tab pane title",
    },
    id: {
      type: String,
      default: null,
      description: "Tab pane id",
    },
  },
  inject: ["addTab", "removeTab"],
  data() {
    return {
      active: false,
    };
  },
  mounted() {
    this.addTab(this);
  },
  unmounted() {
    if (this.$el && this.$el.parentNode) {
      this.$el.parentNode.removeChild(this.$el);
    }
    this.removeTab(this);
  },
};


</script>
<style></style>
