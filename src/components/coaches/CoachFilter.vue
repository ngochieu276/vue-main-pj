<template>
  <base-card>
    <h2>Find your Coach</h2>
    <span> 
        <input type="checkbox" id="frontend" checked @change="setFilter">
        <label for="frontend">Frontend</label>
    </span>
     <span> 
        <input type="checkbox" id="backend" checked @change="setFilter">
        <label for="backend">Backend</label>
    </span>
     <span> 
        <input type="checkbox" id="career" checked @change="setFilter">
        <label for="career">Carrer</label>
    </span>
  </base-card>
</template>

<script>
import BaseCard from "../UI/BaseCard.vue";
export default {
  components: { BaseCard },
  emits: ['change-filter'],
  data() {
      return {
          filter: {
              frontend: true,
              backend: true,
              career: true
          }
      }
  },
  methods: {
      setFilter(event) {
         const inputId = event.target.id;
         const isActive = event.target.checked;

         const updatedFilters = {
             ...this.filter,
             [inputId]: isActive
         }
         this.filter = updatedFilters;
         console.log(this.filter)
         this.$emit('change-filter',updatedFilters)
      }
  }
};
</script>