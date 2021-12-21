<template>
  <div class="container-fluid text-center p-2 mt-2">
	  <h3>&copy; Dr. Madrix {{year}}</h3>
  </div>
</template>

<script>
export default {
    computed: {
        year(){
           return new Date().getFullYear();
        }
    }

}
</script>
<style scoped>


	h3{
		font-family: 'Fjalla One', sans-serif;
		font-size: 2rem !important;
	}

</style>