<template>
  <div>
	<h1>Twoj email: {{ email }} </h1>
	<div v-if="!logLogged">
		Zaloguj sie emailem:
		<input type ="text" v-model="email">
		<div v-if="email.length < 10">Ale masz krótki adres!</div>
		<div v-else-if="email.length < 15">Twój adres e-mail jest w sam raz.</div>
		<div v-else>Twój adres e-mail jest stanowczo za długi.</div>
		<button @click="logIn()">Zaloguj</button>
	</div>	
	
	<div v-else="logLogged">
	<h2>Witaj {{ email }}</h2>
	<button @click="logOut()">Wyloguj</button>
	</div>
	</div>
	
	

</template>

<script>
import "milligram";
export default {
	data (){
		return {
			email: ''
			,logLogged: false
		}
	},
	methods: {
		alertMyEmail() {
			alert(this.email);
			}	
		,logIn (){
			this.logLogged = true
			}
		,logOut(){
			this.logLogged = false
		},
	},
  }

</script>

<style>

</style>
