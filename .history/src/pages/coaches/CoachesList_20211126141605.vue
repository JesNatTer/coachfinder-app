<template>
    <section>Filter</section>
    <section>
        <div class="controls">
            <button>Refresh</button>
            <router-link to="/register">Register as Coach</router-link>
        </div>
        <ul>
            <li v-for="coach in filteredCoaches" :key="coach.id"></li>
        </ul>
    </section>
</template>

<script>
export default {
    computed: {
        filteredCoaches() {
            return this.$store.getters['coaches/coaches']
        }
    }
}
</script>

<style>

</style>