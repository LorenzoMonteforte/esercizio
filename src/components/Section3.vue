<script>
export default {
    name: "Section3",
    data() {
        return {
            firstStages: [
                {
                    title: "Demo Classes",
                    paragraph: "In the first week, students try to accommodate with the teaching style and choose their optional courses."
                },
                {
                    title: "Graduation Day",
                    paragraph: "On the day of graduation, all students gather for the ceremony and then network and party among others."
                }
            ],
            secondStages: [
                {
                    title: "Orientation",
                    paragraph: "First day of the university year, all students gather for the opening ceremony and then network with others."
                },
                {
                    title: "Evaluation",
                    paragraph: "At the end of a semester, students take a general evaluation test for every subject they're learning."
                }
            ]
        }
    }
}
</script>

<template>
    <section>
        <div id="dividerContainer">
            <img src="../assets/img/svg-0.svg" alt="Divisore a forma di onda">
        </div>
        <div id="universityYear">
            <img src="../assets/img/Clock-and-Bell.png" alt="Orologio e sveglia">
            <h2>University Year</h2>
            <div>
                <div>
                    <div class="stage" v-for="firstStage in firstStages">
                        <h3>{{ firstStage.title }}</h3>
                        <p>{{ firstStage.paragraph }}</p>
                    </div>
                </div>
                <img src="../assets/img/Timeline-Item.png" alt="Linea cronologica">
                <div>
                    <div class="stage stageBis" v-for="secondStage in secondStages">
                        <h3>{{ secondStage.title }}</h3>
                        <p>{{ secondStage.paragraph }}</p>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<style scoped>
section {
    height: 1000px;
    background-color: red;
}

#dividerContainer {
    overflow: hidden;
    background-color: white;
}

#dividerContainer>img {
    display: block;
}

#universityYear {
    margin-top: 6rem;
    display: flex;
    flex-direction: column;
    align-items: center;
}

#universityYear>img {
    width: 5%;
}

#universityYear>h2 {
    margin-top: 1rem;
    font-size: 3rem;
    color: white;
}

#universityYear>div {
    width: 100%;
    margin-top: 6rem;
    padding: 0 4rem;
}

#universityYear>div>img {
    width: 100%;
}

.stage {
    width: 40%;
    padding: 0 2rem 1rem 2rem;
}

.stage>h3 {
    text-align: center;
    color: white;
}

.stage>p {
    margin-top: 1rem;
    text-align: center;
    color: white;
}

#universityYear>div>div:first-of-type {
    display: flex;
    justify-content: flex-end;
}

.stageBis {
    padding-top: 1rem;
    padding-bottom: 0;
}

#universityYear>div>div:last-of-type {
    display: flex;
}
</style>