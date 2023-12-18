<script>
export default {
    name: "DescriptionImage",
    props: {
        content: Object,
        style: Object
    },
    methods: {
        getImagePath: function (img) {
            return new URL(`../assets/${img}`, import.meta.url).href;
        }
    }
}
</script>

<template>
    <div id="descriptionImage">
        <div :class="style.descriptionImage == false ? 'order2' : ''">
            <img :src="getImagePath(content.srcIcon)" :alt="content.altIcon" v-if="style.icon == true">
            <h2 :class="style.icon == false ? 'marTop0' : ''">{{ content.title }}</h2>
            <p>{{ content.paragraph }}</p>
            <button class="btn btnYel" :class="style.btnColor == 'red' ? 'btnRed' : ''">
                <strong>{{ content.button }}</strong>
            </button>
        </div>
        <div :class="[style.descriptionImage == false ? 'order1' : '', style.centredImage == true ? 'centredImage' : '']">
            <img :class="style.centredImage == true ? 'wid55' : ''" :src="getImagePath(content.srcImg)"
                :alt="content.altImg">
        </div>
    </div>
</template>

<style scoped>
#descriptionImage {
    display: flex;
}

#descriptionImage>div {
    width: 50%;
}

#descriptionImage>div:first-child>img {
    width: 10%;
}

#descriptionImage>div:first-child {
    padding: 6rem 1rem 6rem 5rem;
}

#descriptionImage>div:first-child>h2 {
    margin-top: 1rem;
    font-size: 3rem;
}

#descriptionImage>div:first-child>p {
    margin-top: 2rem;
}

#descriptionImage>div:first-child>button {
    margin-top: 2rem;
}

#descriptionImage>div:last-child>img {
    width: 85%;
}

#descriptionImage>div:last-child {
    display: flex;
    align-items: center;
    padding-left: 1rem;
}

.order1 {
    order: 1;
    padding-left: 0 !important;
    justify-content: flex-end;
    padding-right: 1rem;
}

.order2 {
    order: 2;
    padding: 6rem 5rem 6rem 1rem !important;
}

.centredImage {
    padding-left: 0 !important;
    padding-right: 0 !important;
    justify-content: center !important;
}

.wid55 {
    width: 55% !important;
}

.marTop0 {
    margin-top: 0 !important;
}

.btnRed {
    color: white;
    background-color: rgba(218, 108, 110, 1);
}
</style>