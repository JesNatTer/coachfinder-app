<template>
    <section>Filter</section>
    <base-card>
        <section>
            <div class="controls">
                <base-button mode='outline'>Refresh</base-button>
                <base-button link to="/register">Register as Coach</base-button>
            </div>
            <ul v-if="hasCoaches">
                <CoachItem v-for="coach in filteredCoaches" :key="coach.id" :id="coach.id" :first-name="coach.firstName" :last-name="coach.lastName" :rate="coach.hourlyRate" :areas="coach.areas"
                ></CoachItem>
            </ul>
            <h3 v-else>No coaches found.</h3>
        </section>
    </base-card>
</template>

<script>
import CoachItem from "../../components/coaches/CoachItem.vue"
import BaseButton from '../../components/ui/BaseButton.vue'
export default {
    components: {CoachItem, BaseButton},
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

<style scoped>
ul {
  list-style: none;
  margin: 0;
  padding: 0;
}

.controls {
  display: flex;
  justify-content: space-between;
}
</style>