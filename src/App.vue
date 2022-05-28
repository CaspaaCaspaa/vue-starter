<template>
  <div>
	<h1>Twoj email: {{ email }} </h1>
	<input type ="text" v-model="email">
  </div>
</template>

<script>

export default {
	data (){
	return {
	email: ''
	}
	}
  }

</script>

<style>

</style>
