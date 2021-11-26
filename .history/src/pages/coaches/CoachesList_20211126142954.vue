<template>
    <section>Filter</section>
    <section>
        <div class="controls">
            <button>Refresh</button>
            <router-link to="/register">Register as Coach</router-link>
        </div>
        <ul v-if="hasCoaches">
            <CoachItem/>
        </ul>
        <h3 v-else>No coaches found.</h3>
    </section>
</template>

<script>
import CoachItem from "../../components/coaches/CoachItem.vue"
export default {
    computed: {
        filteredCoaches() {
            return this.$store.getters['coaches/coaches']
        },
        hasCoaches() {
            return this.$store.getters['coaches/hasCoaches']
        }
    }
}
</script>

<style>

</style>