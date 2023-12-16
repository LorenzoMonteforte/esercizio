<script>
export default {
    name: "Navbar",
    props: {
        navbarItems: Array
    }
}
</script>

<template>
    <nav>
        <ul>
            <li v-for="navbarItem in navbarItems">
                <strong>
                    {{ navbarItem.title }}
                    <font-awesome-icon class="marLef0_5rem" icon="fa-solid fa-caret-down" v-if="navbarItem.arrow == true" />
                </strong>
            </li>
        </ul>
    </nav>
</template>

<style scoped>
nav>ul {
    list-style-type: none;
    display: flex;
    justify-content: space-between;
}

nav>ul>li:first-of-type {
    color: rgba(232, 210, 89, 255);
}

nav {
    width: 100%;
}

nav>ul>li {
    color: white;
}
</style>