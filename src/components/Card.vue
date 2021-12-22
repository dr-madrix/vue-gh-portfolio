<template>
	<div class="card h-100">
		<div class="card-body d-flex flex-column justify-content-between">
		<h5 class="card-title">{{repoTitle}}</h5>
		<p class="card-text">{{repoDescription}}</p>
		<p>Año: {{repoDate}}</p>
		<div>
			<a :href="repoUrl" class="btn btn-primary mb-1 block" target="_blank">Repositorio</a>
			<a :href="homeUrl" class="btn btn-danger" v-if="homeUrl" target="_blank">Homepage</a>
		</div>
		</div>
	</div>
</template>

<script>
export default {
	props: {
		repoTitle: String,
		repoDescription: String,
		repoDate: String,
		repoUrl: String,
		homeUrl: String
	}

}
</script>

<style>
	.btn{
		display: block !important;
	}

</style>