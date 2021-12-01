<template>
    <section>
        <base-card>
        <h2>Register as a coach now!</h2>
        <coach-form @save-data="saveData"></coach-form>
        </base-card>
        
    </section>
</template>

<script>
import CoachForm from '../../components/coaches/CoachForm.vue'
import BaseCard from '../../components/UI/BaseCard.vue'
export default {
  components: { CoachForm, BaseCard },
  
  methods: {
      saveData(data) {
        this.$store.dispatch('coaches/resgisterCoach',data);
        this.$router.replace('/coaches')
      }
  }
    
}
</script>