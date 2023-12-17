<script>
export default {
    name: "Section2",
    data() {
        return {
            faculties: [
                {
                    srcImg: "img/Gavel-v2.png",
                    title: "Law Faculty"
                },
                {
                    srcImg: "img/Coins-tabs-v2.png",
                    title: "Economy"
                },
                {
                    srcImg: "img/Medicine-tabs-v2.png",
                    title: "Medicine"
                },
                {
                    srcImg: "img/Computer-tabs-v2.png",
                    title: "Computer Science"
                },
                {
                    srcImg: "img/Palette-tabs-v2.png",
                    title: "Graphic Design"
                }
            ]
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
        }
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
    </section>
</template>

<style scoped>
section {
    height: 1000px;
    background-color: red;
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

section>div:last-of-type {
    background-color: white;
    margin-top: 2rem;
    padding: 0 5rem;
    display: flex;
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