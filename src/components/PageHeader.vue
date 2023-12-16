<script>
import Navbar from './Navbar.vue';
import Carousel from './Carousel.vue';
export default {
    name: "PageHeader",
    components: {
        Navbar,
        Carousel
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
            ],
            dataCarousel: [
                {
                    title: "Showcase your courses",
                    paragraph: "EduPrime is the most versatile WordPress theme for educational purpose, showcasing universities, courses, secondary school etc.",
                    srcBackground: "img/theme_slider1_bg-1.jpg"
                },
                {
                    title: "Key to your success",
                    paragraph: "EduPrime is the most versatile WordPress theme for educational purpose, showcasing universities, courses, secondary school etc.",
                    srcBackground: "img/theme_slider2_bg-1.jpg"
                },
                {
                    title: "Lead. Inspire. Win!",
                    paragraph: "EduPrime is the most versatile WordPress theme for educational purpose, showcasing universities, courses, secondary school etc.",
                    srcBackground: "img/theme_slider3_bg-1.jpg"
                }
            ]
        }
    },
    methods: {
        getImagePath: function (img) {
            return new URL(`../assets/${img}`, import.meta.url).href;
        },
        changeBackground: function (indexCarousel) {
            const header = document.getElementById("header");
            header.style.backgroundImage = "url(" + this.getImagePath(this.dataCarousel[indexCarousel].srcBackground) + ")"
        }
    }
}
</script>

<template>
    <header id="header">
        <div id="opaRed">
            <div>
                <div>
                    <img src="../assets/img/theme_eduprime_logo.png" alt="Logo Eduprime">
                </div>
                <div>
                    <Navbar :navbarItems="navbarItems" />
                </div>
                <div>
                    <button class="btn btnYel">
                        <strong>VIEW COURSES</strong>
                    </button>
                </div>
            </div>
            <div>
                <Carousel :dataCarousel="dataCarousel" @invokeChangeBackground="changeBackground" />
            </div>
        </div>
    </header>
</template>

<style scoped>
header {
    height: 1000px;
    background-color: red;
}

#opaRed>div:first-child {
    display: flex;
}

#opaRed>div:first-child>div:first-child,
#opaRed>div:first-child>div:last-child {
    width: 25%;
}

#opaRed>div:first-child>div:nth-child(2) {
    width: 50%;
    display: flex;
    align-items: center;
}

#opaRed>div:first-child>div:first-child>img {
    width: 100%;
}

#opaRed>div:first-child>div:first-child {
    padding-right: 1.5rem;
    display: flex;
    align-items: center;
}

#opaRed>div:first-child>div:last-child {
    display: flex;
    align-items: center;
    padding-left: 1.5rem;
    justify-content: flex-end;
}

#opaRed>div:last-child {
    margin-top: 6rem;
}

#opaRed {
    height: 100%;
    background-color: rgba(218, 108, 110, 0.9);
    padding: 3rem 3rem 0;
}
</style>