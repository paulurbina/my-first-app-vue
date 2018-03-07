<template>
	<div>
		<h1>Componente por defecto</h1>
	</div>
</template>

<script>
	
export default {
	data() {
		return {
			title: 'hola vue',
			users: {
				firstName: 'paul',
				lastName: 'urbina'
			},
			myhtml: '<h2>HTML Aqui</h2>',
			tasks: [
				{ comida: 'pan' },
				{ comida: 'papa' },
				{ comida: 'queso' },
			]
		}
	},
	methods: {
		typing(e) {
			console.log('dio un enter');
		}
	},
	computed: {
		fullName() {
			return this.users.firstName + this.users.lastName;
		}
	},
	props: {
		msg: String,
		default: 'mensaje por defecto'
	}

}

</script>


<style>
	
</style>