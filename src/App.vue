<template>
    <div>
        <headerVue id="header"></headerVue>
        <SearchBarVue></SearchBarVue>
        <InformationVue></InformationVue>
    </div>
</template>

<script setup lang="ts">
import headerVue from './components/header.vue'
import InformationVue from './components/Information.vue'
import SearchBarVue from './components/searchBar.vue'
</script>

<style lang="scss" scoped>
#header {
    position: absolute;
    left: 0;
    top: 0;
    z-index: 100;
    height: 60px;
    padding-left: 24px;
}
</style>
