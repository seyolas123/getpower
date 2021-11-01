<template>
  <div class="">
    <!-- Navbar -->

    <!-- As a heading -->
    <div class="container">
         <nav class="navbar navbar-light bg-grey">
          <span class="navbar-brand mb-0 h1">Buypowers.ng
            <hr>
          </span>
         
        </nav>
        
    </div>
   
    <!-- Page content -->
    <div class="container pb-1">
       
      <router-view></router-view>
    </div>
    
  </div>
 
</template>
<script>
export default {
  name: "auth-layout",
  data() {
    return {
      year: new Date().getFullYear(),
      showMenu: false,
    };
  },
};
</script>
<style></style>
