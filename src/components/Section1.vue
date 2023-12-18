<script>
import DescriptionImage from './DescriptionImage.vue';
export default {
    name: "Section1",
    components: {
        DescriptionImage
    },
    data() {
        return {
            content: {
                srcIcon: "img/Books-icon.png",
                altIcon: "Icona libri",
                title: "Thousands of courses for any type of student",
                paragraph: "At EduPrime, it doesn't matter what domain you wish to pursue a career in. Hereyou can fin a course that satisfies your needs within a click away and applies for a course in a matter of minutes. EduPrime is ranked as the most versatile university in the world, thanks to thenumber of courses it provides.",
                button: "Browse through courses",
                srcImg: "img/Graduation-Illustration.png",
                altImg: "Tocco"
            },
            style: {
                descriptionImage: true,
                centredImage: false,
                icon: true,
                btnColor: "yel"
            }
        }
    }
}
</script>

<template>
    <section>
        <DescriptionImage :content="content" :style="style" />
    </section>
</template>

<style scoped>
section {
    background-image: url("../assets/img/home-background.png");
    background-position-x: 100%;
    background-position-y: 50%;
    background-size: 95%;
    background-repeat: no-repeat;
}
</style>