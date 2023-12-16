<script>
import Navbar from './Navbar.vue';
export default {
    name: "PageHeader",
    components: {
        Navbar
    },
    data() {
        return {
            navbarItems: [
                {
                    title: "Home",
                    arrow: true
                },
                {
                    title: "Courses",
                    arrow: true
                },
                {
                    title: "About Us",
                    arrow: false
                },
                {
                    title: "News",
                    arrow: true
                },
                {
                    title: "Pages",
                    arrow: true
                },
                {
                    title: "Contact",
                    arrow: false
                },
                {
                    title: "Purchase",
                    arrow: false
                }
            ]
        }
    }
}
</script>

<template>
    <header>
        <div>
            <div>
                <img src="../assets/img/theme_eduprime_logo.png" alt="Logo Eduprime">
            </div>
            <div>
                <Navbar :navbarItems="navbarItems" />
            </div>
            <div>
                <button>
                    <strong>VIEW COURSES</strong>
                </button>
            </div>
        </div>
    </header>
</template>

<style scoped>
header {
    height: 1000px;
    background-color: red;
    padding: 3rem 3rem 0;
}

header>div:first-child {
    display: flex;
}

header>div:first-child>div:first-child,
header>div:first-child>div:last-child {
    width: 25%;
}

header>div:first-child>div:nth-child(2) {
    width: 50%;
    display: flex;
    align-items: center;
}

header>div:first-child>div:first-child>img {
    width: 100%;
}

header>div:first-child>div:first-child {
    padding-right: 1.5rem;
    display: flex;
    align-items: center;
}

header>div:first-child>div:last-child {
    display: flex;
    align-items: center;
    padding-left: 1.5rem;
    justify-content: flex-end;
}

header>div:first-child>div:last-child>button {
    font-size: 1rem;
    padding: 1.5rem 3rem;
    border: none;
    border-radius: 2rem;
    color: white;
    background-color: rgba(232, 210, 89, 255);
}
</style>