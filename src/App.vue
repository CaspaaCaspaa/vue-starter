<template>
  <div>
	<h1>Twoj email: {{ email }} </h1>
	<div v-if="!loggedThatsUser">
		<login-form @login="logIn($event)" button-label="wejdź"></login-form>
		<login-form @login="logIn($event)"></login-form>

<!-- 		Zaloguj sie emailem:
		<input type ="text" v-model="email">
		<div v-if="email.length < 10">Ale masz krótki adres!</div>
		<div v-else-if="email.length < 15">Twój adres e-mail jest w sam raz.</div>
		<div v-else>Twój adres e-mail jest stanowczo za długi.</div>
		<button @click="logIn()">Zaloguj</button> -->
	</div>	
	
	<div v-else="loggedThatsUser">
		<log-out :loggedUser="loggedThatsUser" @logout="logOut($event)"></log-out>
	
<!-- 	<h2>Witaj {{ loggedThatsUser }}</h2>
	<button @click="logOut()">Wyloguj</button> -->
	</div>
	</div>
	
	

</template>

<script>
import "milligram";
import LoginForm from "./LoginForm";
import LogOut from "./LogOut";
export default {
	components: {LoginForm,LogOut},
	data (){
		return {
			email: ''
			,loggedThatsUser: false
		}
	},
	methods: {
		alertMyEmail() {
			alert(this.email);
			}	
		,logIn (username){
			this.loggedThatsUser = username;
			}
		,logOut(){
			this.loggedThatsUser = false
		},
	},
  }

</script>

<style>

</style>
