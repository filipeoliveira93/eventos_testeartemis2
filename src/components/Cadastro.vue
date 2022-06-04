<template>
	<div class="box">
		<h3 class="title is-4">Cadastro de Eventos</h3>
		<form @submit="enviarform($event)">
			<div class="">
				<label class="label" for="nome">Nome</label>
				<input
					type="text"
					class="control"
					name="nome"
					placeholder="Nome do evento"
					v-model="nome"
				/>
			</div>
			<div class="field">
				<label class="label" for="data">Data</label>
				<input
					type="date"
					class="control"
					name="data"
					placeholder="Data do evento"
					v-model="data"
				/>
			</div>
			<input type="submit" value="Cadastrar" class="button" />
		</form>
	</div>
	<ul>
		<li v-for="evento in eventos" :key="evento.key">
			{{ evento.nome }} {{ evento.data }}
		</li>
		<!-- realiza uma iteração em todos os objetos dentro do array -->
	</ul>
</template>

<script>
export default {
	name: "CadastroComp",
	components: {},
	data() {
		return {
			key: 1,
			nome: "",
			data: "",
			eventos: [],
			// evento: {}
		};
	},
	methods: {
		enviarform(event) {
			event.preventDefault();
			this.cadastrar();
		},

		cadastrar() {
			// cadastrar evento no array
			this.eventos.push({
				key: this.key,
				nome: this.nome,
				data: this.data,
			});

			this.key++;
			this.nome = "";
			this.data = "";
		},
	},
};
</script>

<style>
@import "https://cdn.jsdelivr.net/npm/bulma@0.9.4/css/bulma.min.css";
</style>
