<script>
export default {
    name: "CurrentSeries",
    props: {
        img: String,
        text: String,
        price: String,
        type: String
    }
}
</script>

<template>
    <div class="col">
        <figure>
            <img :src="img" alt="">
        </figure>
        <h5>{{ text }}</h5>
        <p>A partire da <span>{{ price }}</span></p>
        <p>Categoria: <span id="type">{{ type }}</span></p>
    </div>
</template>

<style lang="scss">
.col {
    width: calc(100% / 6 - 20px + (20px / 6));

    img {
        height: 300px;
    }

    h5 {
        font-size: 20px;
        color: #d6d6d6;
        text-transform: uppercase;
        margin-top: 10px;
    }

    p {
        font-size: 16px;
        color: #d6d6d6;
        margin-block: 5px;

        span {
            color: green;
        }

        #type {
            text-transform: uppercase;
            color: lightsalmon;
        }
    }
}
</style>
