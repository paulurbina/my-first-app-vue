<template>
	<div class="fondo">
		<h1>Componente User</h1>
		<ul>
			<li v-for="user in users">
				{{ user.name }} - {{ user.email }} 
				<button v-on:click="deleteUser(user)"> Delete </button>
			</li>
		</ul>
		<form v-on:submit.prevent="addUser">
			<input type="text" v-model="newUser.name" placeholder="Name" >
			<input type="email" v-model="newUser.email" placeholder="Email" >
			<button type="submit">
				Add
			</button>
		</form>
	</div>
</template>

<script>
	
	export default {
		data() {
			return {
				users: [
					{
						name: 'tony',
						email: 'paulurbian@hotmail.com',
						contacted: false
					},
					{
						name: 'tatiana',
						email: 'tati@hotmail.com',
						contacted: false
					},
					{
						name: 'kevin',
						email: 'kevin@hotmail.com',
						contacted: true
					}
				],
				newUser: {}
			}
		},
		methods: {
			addUser() {
				this.users.push(this.newUser);
				this.newUser = {};
			},
			deleteUser(user) {
				this.users.splice(this.users.indexOf(user), 1);
			}
		},
		created() {
			this.$http.get('https://jsonplaceholder.typicode.com/users')
				.then(res => this.users = res.body);
		}
	}

</script>

<style>
	.fondo {
		background: green;
	}
</style>