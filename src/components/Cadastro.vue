<template>
	<div class="box container">
		<h1>Cadastrar Evento</h1>
		<form class="" action="" @submit="enviarform($event)">
			<div class="">
				<label class="label" for="nome">Nome</label>
				<input
					type="text"
					class="control"
					id="nome"
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
					id="data"
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

/* .form-group {
	margin-bottom: 1rem;
	background-color: #dbbebe;
	padding: 1rem;
	border-radius: 5px;
	display: flex;
	flex-direction: column;
	justify-content: space-around;
	align-items: center;
	height: 200px;
}

.form-input {
    display: flex;
    flex-direction: row;
    justify-content: space-around;
    align-items: center;
    background-color: #ffffff;
    padding: 0.4rem;
    margin: 0.2rem;
    width: 300px;
} */
</style>
