<template>
  <div class="row justify-content-center">
    <div class="col-lg-5 col-md-7">
      <div class="card bg-secondary shadow border-0">
        
        <div class="card-body px-lg-5 py-lg-5">
          <div class="text-center text-muted mb-4">
            <small>sign in with credentials</small>
          </div>
          <form role="form">
            <base-input
              formClasses="input-group-alternative mb-3"
              placeholder="Enter your Phone number"
              addon-left-icon="ni ni-phone"
              v-model="model.phone"
            >
            </base-input>

            <div class="text-center">
              <base-button :disabled="isdisabled" type="primary" v-on:click="login()" class="my-4">Continue</base-button>
            </div>
          </form>

        <div v-if="logged" class="container height-100 d-flex justify-content-center align-items-center">
          <div class="position-relative">
              <div class="card p-2 text-center">
                  <h6>Please enter the one time password <br> </h6>
                  <div> <span> sent to</span> <small>+1******4343</small> </div>
                  <div id="otp" class="inputs d-flex flex-row justify-content-center mt-2"> <input class="m-2 text-center form-control rounded" type="text" id="input1" v-on:keyup="inputenter(1)" maxlength="1" /> <input class="m-2 text-center form-control rounded" v-on:keyup="inputenter(2)" type="text" id="input2" maxlength="1" /> <input class="m-2 text-center form-control rounded" v-on:keyup="inputenter(3)" type="text" id="input3" maxlength="1" /> <input class="m-2 text-center form-control rounded" v-on:keyup="inputenter(4)" type="text" id="input4" maxlength="1" /> </div>
                  <div class="mt-4"> <button class="btn btn-danger px-4 validate">Validate</button> </div>
                  <div class="mt-3 content d-flex justify-content-center align-items-center"> <span>Didn't get the code</span> <a href="#" class="text-decoration-none ms-3">Resend(1/3)</a> </div>
              </div>
          </div>

          <router-link to="/dashboardmini" class="text-light"
            ><small>Go to Dashboard</small></router-link
          >
       </div>

        </div>
      </div>
      <div class="row mt-3">
        <div class="col-6">
          <a href="#" class="text-light"><small>Forgot password?</small></a>
        </div>
        <div class="col-6 text-right">
          <router-link to="/register" class="text-light"
            ><small>Create new account</small></router-link
          >
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: "login",
  data() {
    return {
      model: {
        phone: "",
      },
      logged: false,
    };
  },

  computed: {
    isdisabled() {
      return (
        this.model.phone == ''
      );
    }
  },

  methods: {
    login() {
      if(this.model.phone == '08023682022'){
        //alert('<div class="alert alert-success">success loggen in</div>');
        this.logged=true;
        //redirect('/dashboard');
      }else {
        //alert('<div class="alert alert-danger">wrong loggen in</div>');
      }
    }
  }
};
</script>
<style></style>
