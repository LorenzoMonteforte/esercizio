<script>
import DescriptionImage from './DescriptionImage.vue';
export default {
    name: "Section2",
    components: {
        DescriptionImage
    },
    data() {
        return {
            faculties: [
                {
                    srcImg: "img/Gavel-v2.png",
                    title: "Law Faculty",
                    srcImg2: "img/Gavel-Illustration-e1556884768193.png",
                    paragraph: "Learning from world-leading academics and practitioners, you'll not only receive an outstanding grounding in the theory of law, but you will be able to understand how those principles are applied in practice through a range of student-led activities and competitions."
                },
                {
                    srcImg: "img/Coins-tabs-v2.png",
                    title: "Economy",
                    srcImg2: "img/Economy.png",
                    paragraph: "Economics focuses on the behaviour and interactions of economic agents and how economies work. Microeconomics analyzes basic elements in the economy, including individual agents and markets, their interactions, and the outcomes of interactions, including unemployment of resource."
                },
                {
                    srcImg: "img/Medicine-tabs-v2.png",
                    title: "Medicine",
                    srcImg2: "img/Medicine.png",
                    paragraph: "Medicine is the science and practice of estabilishing the diagnosis, prognosis, treatment, and prevention of disease. Medicine encompasses a variety of health care practices evolved to maintain and restore health by the prevention and treatment of illness."
                },
                {
                    srcImg: "img/Computer-tabs-v2.png",
                    title: "Computer Science",
                    srcImg2: "img/Computer-Science.png",
                    paragraph: "Computer science is the study of processes that interact with data and that can be represented as data in the form of programs. It enables the use of algorithms to manipulate, store, and communicate digital information. A computer scientist studies the theory of computation software systems."
                },
                {
                    srcImg: "img/Palette-tabs-v2.png",
                    title: "Graphic Design",
                    srcImg2: "img/Graphic-Design.png",
                    paragraph: "Graphic design is the process of visual communication and problem-solving through the use of typography, photography and illustration. The field is considered a subset of visual communication and communication design, but sometimes the term ''graphic design'' is used synonymously.'"
                }
            ],
            content: {
                title: "",
                paragraph: "",
                button: "Read More",
                srcImg: "",
                altImg: ""
            },
            style: {
                descriptionImage: false,
                centredImage: true,
                icon: false,
                btnColor: "red"
            }
        }
    },
    methods: {
        getImagePath: function (img) {
            return new URL(`../assets/${img}`, import.meta.url).href;
        },
        selectCard: function (indexCard) {
            const imgCards = document.getElementsByClassName("imgCard");
            const h3Cards = document.getElementsByClassName("h3Card");
            const cards = document.getElementsByClassName("card");
            const squareCards = document.getElementsByClassName("squareCard");
            for (let i = 0; i < this.faculties.length; i++) {
                imgCards[i].style.filter = "none";
                h3Cards[i].style.color = "rgba(218, 108, 110, 1)";
                cards[i].style.backgroundColor = "white";
                cards[i].style.border = "1px solid lightgray";
                squareCards[i].style.display = "none";
            }
            imgCards[indexCard].style.filter = "brightness(0) invert(1)";
            h3Cards[indexCard].style.color = "white";
            cards[indexCard].style.backgroundColor = "rgba(218, 108, 110, 1)";
            cards[indexCard].style.border = "1px solid rgba(218, 108, 110, 1)";
            squareCards[indexCard].style.display = "block";
            this.content.title = this.faculties[indexCard].title;
            this.content.paragraph = this.faculties[indexCard].paragraph;
            this.content.srcImg = this.faculties[indexCard].srcImg2;
            this.content.altImg = this.faculties[indexCard].title;
        }
    },
    mounted() {
        this.selectCard(0);
    }
}
</script>

<template>
    <section>
        <h2>Faculties available at EduPrime</h2>
        <div>
            <p>
                A single university with a load of courses, tailored to satisfy any student's needs.
            </p>
        </div>
        <div>
            <div class="card" v-for="(faculty, indexCard) in faculties" @click="selectCard(indexCard)">
                <img class="imgCard" :src="getImagePath(faculty.srcImg)" :alt="faculty.title">
                <h3 class="h3Card">{{ faculty.title }}</h3>
                <div class="squareCard"></div>
            </div>
        </div>
        <DescriptionImage :content="content" :style="style" />
    </section>
</template>

<style scoped>
section {
    padding-top: 6rem;
}

section>h2 {
    text-align: center;
    font-size: 3rem;
}

section>div:first-of-type {
    margin-top: 2rem;
    display: flex;
    justify-content: center;
}

section>div:first-of-type>p {
    width: 25%;
    text-align: center;
}

section>div:nth-of-type(2) {
    background-color: white;
    margin-top: 2rem;
    padding: 0 5rem;
    display: flex;
    box-shadow: 1px 1px 25px 1px lightgray;
}

.card {
    height: 100%;
    width: 20%;
    border: 1px solid lightgray;
    padding: 2rem 0;
    display: flex;
    flex-direction: column;
    align-items: center;
    position: relative;
    background-color: white;
}

.card>img {
    width: 40%;
}

.card:first-of-type>img {
    filter: brightness(0) invert(1);
}

.card>h3 {
    margin-top: 1rem;
    font-size: 1rem;
    color: rgba(218, 108, 110, 1);
}

.card:first-of-type>h3 {
    color: white;
}

.card>div {
    height: 1.5rem;
    width: 1.5rem;
    background-color: rgba(218, 108, 110, 1);
    position: absolute;
    left: 50%;
    bottom: 0;
    translate: -50% 50%;
    transform: rotate(45deg);
    display: none;
}

.card:first-of-type>div {
    display: block;
}

.card:first-of-type {
    background-color: rgba(218, 108, 110, 1);
    border: 1px solid rgba(218, 108, 110, 1);
}
</style>