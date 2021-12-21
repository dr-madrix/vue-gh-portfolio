<template>
	<div class="container-fluid text-center p-2">
		<h1 class="mt-2">{{headerTitle}}</h1>
	</div>
</template>

<script>
export default {
	props:{
		headerTitle: String
	}
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Fjalla+One&display=swap');

	.container-fluid{
		background: #FFD166;
	}

	h1{
		font-family: 'Fjalla One', sans-serif;
		font-size: 3rem !important;
	}

</style>