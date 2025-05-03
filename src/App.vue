<template>
  <div>
    <the-header></the-header>
    <!-- <TheHeader /> -->
    <button
      @click="setSelectedComponent('active-goals')"
      class="border-2 border-amber-200 p-2">
      Active Goals
    </button>
    <button
      @click="setSelectedComponent('manage-goals')"
      class="border-2 border-amber-200 p-2">
      Manage Goals
    </button>
    <!-- <active-goals v-if="selectedComponent === 'active-goals'"></active-goals>
    <manage-goals v-if="selectedComponent === 'manage-goals'"></manage-goals> -->
    <keep-alive>
      <component :is="selectedComponent"></component>
    </keep-alive>
  </div>
</template>

<script>
import TheHeader from './components/TheHeader.vue'
import ActiveGoals from './components/ActiveGoals.vue'
import ManageGoals from './components/ManageGoals.vue'

export default {
  components: {
    TheHeader,
    ActiveGoals,
    ManageGoals,
  },
  data() {
    return {
      selectedComponent: 'active-goals',
      activeUser: {
        name: 'Nakashima Yuzuki',
        description: 'Site owner and admin',
        role: 'admin',
      },
    }
  },
  methods: {
    setSelectedComponent(cmp) {
      this.selectedComponent = cmp
    },
  },
}
</script>

<style>
html {
  font-family: sans-serif;
}

body {
  margin: 0;
}
</style>
