<script>
export default {
    name: "AppMain",
    data() {
        return {
            infoItems: [
                {
                    src: 'buy-comics-digital-comics.png',
                    info: 'digital comics'
                },
                {
                    src: 'buy-comics-merchandise.png',
                    info: 'dc merchandise'
                },
                {
                    src: 'buy-comics-shop-locator.png',
                    info: 'comic shop locator'
                },
                {
                    src: 'buy-comics-subscriptions.png',
                    info: 'dc power visa'
                },
                {
                    src: 'buy-dc-power-visa.svg',
                    info: 'dc power visa'
                },

            ]

        }
    },
    methods: {
        getImagePath: function (img) {
            return new URL(`../assets/img/${img}`, import.meta.url).href;
        }
    },

}



</script>

<template>
    <main>
        <div class="bg_black">
            <div class="container">
                <p> -- Content goes here -- </p>
            </div>
        </div>
        <div class="bg_blue">

            <div class="container info">
                <div v-for="(item, index) in  infoItems " :key="index" class="infoContent">
                    <figure>
                        <img :src="getImagePath(item.src)" alt="{{ item.info }}">
                    </figure>
                    <p>{{ item.info }}</p>
                </div>
            </div>
        </div>
    </main>
</template>

<style lang="scss" scoped>
.bg_black {

    background-color: #1C1C1C;

    .container {
        padding: 50px;


        >p {
            font-size: 50px;
            color: #fff;
            font-weight: 600;
        }
    }

}

.bg_blue {
    background-color: #0282F9;

    .info {
        padding: 50px;
        display: flex;
        justify-content: space-between;
        gap: 20px;

        .infoContent {
            display: flex;
            gap: 10px;
            align-items: center;

            >figure {
                width: 60px;
            }

            >p {
                color: #fff;
                text-transform: uppercase;
                font-size: 20px;
            }
        }

    }
}
</style>
