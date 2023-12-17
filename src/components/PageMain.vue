<script>
import Section1 from './Section1.vue';
import Section2 from './Section2.vue';
export default {
    name: "PageMain",
    components: {
        Section1,
        Section2
    }
}
</script>

<template>
    <main>
        <Section1 />
        <Section2 />
    </main>
</template>

<style scoped>
main {
    height: 1000px;
}
</style>