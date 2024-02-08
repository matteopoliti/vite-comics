<script>
import CurrentSeries from './CurrentSeries.vue';

export default {
    name: "AppMain",
    components: {
        CurrentSeries
    },
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

            ],
            dcComics: [
                {
                    "thumb": "https://www.coverbrowser.com/image/action-comics/1-1.jpg",
                    "price": "$19.99",
                    "series": "Action Comics",
                    "type": "comic book",
                },
                {
                    "thumb": "https://www.panini.it/media/catalog/product/cache/a5b5dd3adfe0d321084804c738f29601/M/1/M1BLLA015ISBN_0.jpg",
                    "price": "$3.99",
                    "series": "American Vampire 1976",
                    "type": "comic book",
                },
                {
                    "thumb": "https://media.wired.com/photos/593384dad80dd005b42b2817/master/w_2560%2Cc_limit/Aquaman-16.jpg",
                    "price": "$16.99",
                    "series": "Aquaman",
                    "type": "graphic novel",
                },
                {
                    "thumb": "https://d29xot63vimef3.cloudfront.net/image/batgirl/1-1.jpg",
                    "price": "$2.99",
                    "series": "Batgirl",
                    "type": "comic book",
                },
                {
                    "thumb": "https://static.posters.cz/image/750/locandine-film-in-plexiglass-batman-prowl-comic-cover-i69653.jpg",
                    "price": "$3.99",
                    "series": "Batman",
                    "type": "comic book",
                },
                {
                    "thumb": "https://static.wikia.nocookie.net/marvel_dc/images/5/50/Batman_Beyond_v.1_1.jpg",
                    "price": "$2.99",
                    "series": "Batman Beyond",
                    "type": "comic book",
                },
                {
                    "thumb": "https://static.wikia.nocookie.net/marvel_dc/images/0/0d/Batman_Superman_Vol_1_1.jpg",
                    "price": "$3.99",
                    "series": "Batman/Superman",
                    "type": "comic book",
                },
                {
                    "thumb": "https://static.wikia.nocookie.net/marvel_dc/images/c/cf/Batman_Superman_Annual_Vol_2_1.jpg",
                    "price": "$4.99",
                    "series": "Batman/Superman Annual",
                    "type": "comic book",
                },
                {
                    "thumb": "https://static.wikia.nocookie.net/marvel_dc/images/5/54/Batman_The_Joker_War_Zone_Vol_1_1.jpg",
                    "price": "$5.99",
                    "series": "Batman: The Joker War Zone",
                    "type": "comic book",
                },
                {
                    "thumb": "https://static.wikia.nocookie.net/marvel_dc/images/6/64/Batman_Three_Jokers_Collected.jpg",
                    "price": "$6.99",
                    "series": "Batman: Three Jokers",
                    "type": "comic book",
                },
                {
                    "thumb": "https://static.wikia.nocookie.net/marvel_dc/images/f/f8/Batman_White_Knight_Presents_Harley_Quinn_Vol_1_1.jpg",
                    "price": "$4.99",
                    "series": "Batman: White Knight Presents: Harley Quinn",
                    "type": "comic book",
                },
                {
                    "thumb": "https://static.wikia.nocookie.net/marvel_dc/images/c/c8/Catwoman_Vol_2_1.jpg",
                    "price": "$16.99",
                    "series": "Catwoman",
                    "type": "graphic novel",
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
        <div class="jumbo">
        </div>
        <div class="bg_black">
            <div class="container">
                <h2>Current series</h2>

                <div class="comics">

                    <CurrentSeries v-for="(item, index) in dcComics" :key="index" :img="item.thumb" :text="item.series"
                        :price="item.price" :type="item.type" />


                </div>
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
@use "../styles/partials/variables" as *;

.jumbo {
    background-image: url("../assets/img/jumbotron.jpg");
    background-repeat: no-repeat;
    background-size: cover;
    height: 600px;

}

.bg_black {

    background-color: #1C1C1C;

    .container {
        padding-block: 50px;


        h2 {
            color: #fff;
            background-color: $linkHover;
            padding: 10px;
            font-size: 40px;
            text-align: center;
            width: 300px;
            text-transform: uppercase;
            position: relative;
            top: -75px;
            left: 0;
        }

        .comics {
            display: flex;
            gap: 20px;
            flex-wrap: wrap;
        }
    }

}

.bg_blue {
    background-color: $linkHover;

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
