<template>
  <div id="signup">
    <div class="form-group">
      <div class="col-xs-10 col-xs-offset-1">
        <input type="text" v-model="userSignUp" class="form-control input-text" placeholder="usuario">
      </div>
    </div>
    <div class="form-group">
      <div class="col-xs-10 col-xs-offset-1">
        <input type="email" v-model="emailSignUp" class="form-control input-text" placeholder="email">
      </div>
    </div>
    <div class="form-group">
      <div class="col-xs-10 col-xs-offset-1">
        <input type="password" v-model="passwordSignUp" class="form-control input-text" placeholder="contraseña">
      </div>
    </div>
    <button @click="signUp" class="btn btn-default button-submit">Registrar</button>
  </div>
</template>
<script>
  import {mapActions, mapGetters} from 'vuex'
  export default {
    data () {
      return {
        userSignUp: '',
        emailSignUp: '',
        passwordSignUp: ''
      }
    },
    computed: {
      ...mapGetters(['authError'])
    },
    methods: {
      ...mapActions(['createUser', 'authenticate', 'authenticateAnonymous', 'resetAuthError']),
      signUp () {
        let method = this.createUser
        method({email: this.emailSignUp, password: this.passwordSignUp})
      }
    }
  }
</script>
<style scoped>
	@import url(https://fonts.googleapis.com/css?family=Exo:100,200,400);
	@font-face {
		font-family: "pokemonsolid";
		src: url(~/assets/font/pokemonsolid.ttf) format("truetype");
	}
	.input-text {
		transition: .8s;
    background-color: rgba(0,0,0,.5);
    color: white;
    border-color: #006;
		border-bottom-color: white;
    border-bottom-style: groove;
		border-left: none;
		border-right: none;
		border-top: none;
		border-width: 4px;
    width: 220px;
    height: 40px;
	}
	.button-submit {
    background-color: white;
		color: #00acc1;
		width: 100%;
		height: 30px;
		border-radius: 3px;
		font-size: 0.8rem;
		margin-left: 0;
	}
  .input-text:hover {
		transition: .8s;
		background-color: rgba(55,71,79 ,.5);
		color: white;
		box-shadow: inset;
    border-bottom-color: #00acc1;
	}
  .input-text:focus {
		transition: .8s;
		border-bottom-color: white;
  }
</style>
