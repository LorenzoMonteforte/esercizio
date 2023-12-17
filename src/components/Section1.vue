<script>
export default {
    name: "Section1"
}
</script>

<template>
    <section>
        <div>
            <img src="../assets/img/Books-icon.png" alt="Icona libri">
            <h2>Thousands of courses for any type of student</h2>
            <p>
                At EduPrime, it doesn't matter what domain you wish to pursue a career in. Hereyou can fin a course that
                satisfies your needs within a click away and applies for a course in a matter of minutes. EduPrime is ranked
                as the most versatile university in the world, thanks to thenumber of courses it provides.
            </p>
            <button class="btn btnYel">
                <strong>Browse through courses</strong>
            </button>
        </div>
        <div>
            <img src="../assets/img/Graduation-Illustration.png" alt="Tocco">
        </div>
    </section>
</template>

<style scoped>
section {
    display: flex;
    background-image: url("../assets/img/home-background.png");
    background-position-x: 100%;
    background-position-y: 50%;
    background-size: 95%;
    background-repeat: no-repeat;
}

section>div {
    width: 50%;
}

section>div:first-child>img {
    width: 10%;
}

section>div:first-child {
    padding: 6rem 1rem 6rem 5rem;
}

section>div:first-child>h2 {
    margin-top: 1rem;
    font-size: 3rem;
}

section>div:first-child>p {
    margin-top: 2rem;
}

section>div:first-child>button {
    margin-top: 2rem;
}

section>div:last-child>img {
    width: 95%;
}

section>div:last-child {
    display: flex;
    align-items: center;
    padding-right: 5rem;
    padding-left: 1rem;
}
</style>