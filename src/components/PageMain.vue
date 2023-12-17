<script>
import Section1 from './Section1.vue';
export default {
    name: "PageMain",
    components: {
        Section1
    }
}
</script>

<template>
    <main>
        <Section1 />
    </main>
</template>

<style scoped>
main {
    height: 1000px;
}
</style>