<template>
  <div class="container login-container j">
            <div class="row">
                <form @submit.prevent="registration" class="col login-form-1">
                    <h3>Register</h3>

                    <div class="form-group">
                        <input type="text" class="form-control" placeholder="Your Email *" v-model="costumerRegistration.email" />
                    </div>
                    <div class="form-group">
                        <input type="password" class="form-control" placeholder="Your Password *" v-model="costumerRegistration.password"/>
                    </div>
                    <div class="form-group">
                        <input type="submit" class="btnSubmit" value="Submit" />
                    </div>
                </form>
            </div>
  </div>
</template>

<script>
export default {
  name: 'Panel',
  data () {
    return {
      costumerRegistration: {
        email: '',
        password: ''
      }
    }
  },
  methods: {
    registration () {
      console.log('MASUK REGISTER SIS', this.costumerRegistration)
      this.$store.dispatch('registrationCostumer', this.costumerRegistration)
        .then(costumer => {
          this.$router.push('/login')
        })
        .catch(err => {
          console.log(err)
        })
    }
  }
}
</script>

<style>
.login-container{
    margin-top: 5%;
    margin-bottom: 5%;
}
.login-logo{
    position: relative;
    margin-left: -41.5%;
}
.login-logo img{
    position: absolute;
    width: 20%;
    margin-top: 19%;
    background: #282726;
    border-radius: 4.5rem;
    padding: 5%;
}
.login-form-1{
    padding: 9%;
    background:#282726;
    box-shadow: 0 5px 8px 0 rgba(0, 0, 0, 0.2), 0 9px 26px 0 rgba(0, 0, 0, 0.19);
}
.login-form-1 h3{
    text-align: center;
    margin-bottom:12%;
    color:#fff;
}
.login-form-2{
    padding: 9%;
    background: #f05837;
    box-shadow: 0 5px 8px 0 rgba(0, 0, 0, 0.2), 0 9px 26px 0 rgba(0, 0, 0, 0.19);
}
.login-form-2 h3{
    text-align: center;
    margin-bottom:12%;
    color: #fff;
}
.btnSubmit{
    font-weight: 600;
    width: 50%;
    color: #282726;
    background-color: #fff;
    border: none;
    border-radius: 1.5rem;
    padding:2%;
}
.btnForgetPwd{
    color: #fff;
    font-weight: 600;
    text-decoration: none;
}
.btnForgetPwd:hover{
    text-decoration:none;
    color:#fff;
}
</style>
