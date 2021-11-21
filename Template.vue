<template>
  <h2>Component C</h2>
  <ComponentE />
</template>

<script>
import importedComponentName from './ComponentE'
export default {
  name: 'ComponentC',
  components: {
    importedComponentName,
  },
   props: {
    modelValue: String,
  },
  data() {
    return {
      name: '',
    }
  },
   methods: {
    closePopup(name) {
      this.showPopup = false
      console.log('name', name)
    },
  },
   provide() {
    return {
      userName: this.name,
    }
  },
}
</script>

<style scoped>
</style>
