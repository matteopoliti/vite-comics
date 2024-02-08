<script>
export default {
    name: "AppFooter",
    data() {
        return {

            DcComics: [
                'Characters',
                'Comics',
                'Movies',
                'TV',
                'Games',
                'Videos',
                'News'
            ],


            Shop: [
                'Shop DC',
                'Shop DC Collectibles'
            ],
            Dc: [
                'Terms Of Use',
                'Privacy policy (New)',
                'Ad Choices',
                'Advertising',
                'Jobs',
                'Subscriptions',
                'Talent Workshops',
                'CPSC Certificates',
                'Ratings',
                'Shop Help',
                'Contact Us'
            ],

            Sites: [
                'DC',
                'MAD Magazine',
                'DC Kids',
                'DC Universe',
                'DC Power Visa'
            ],
            socials: [
                "footer-facebook.png",
                "footer-twitter.png",
                "footer-youtube.png",
                "footer-pinterest.png",
                "footer-periscope.png",
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
    <footer>
        <div class="bg_image">
            <div class="container link">
                <div>
                    <h3>DC COMICS</h3>
                    <ul>
                        <li v-for="(item, index) in DcComics" :key="index">{{ item }}</li>
                    </ul>
                    <h3>SHOP</h3>
                    <ul>
                        <li v-for="(item, index) in Shop" :key="index">{{ item }}</li>
                    </ul>
                </div>

                <div>
                    <h3>DC</h3>
                    <ul>
                        <li v-for="(item, index) in Dc" :key="index">{{ item }}</li>
                    </ul>
                </div>

                <div>
                    <h3>SITES</h3>
                    <ul>
                        <li v-for="(item, index) in Sites" :key="index">{{ item }}</li>
                    </ul>
                </div>

            </div>
        </div>
        <div class="contacts">
            <div class="container">
                <a href="#" id="sign">sign-up now!</a>

                <div class="social">
                    <span>follow us</span>
                    <a href="#" v-for="(item, index) in socials" :key="index">
                        <img :src="getImagePath(item)" alt="">
                    </a>
                </div>

            </div>
        </div>
    </footer>
</template>

<style lang="scss" scoped>
@use "../styles/partials/variables" as *;

.bg_image {
    background-image: url("../assets/img/footer-bg.jpg");
    background-repeat: no-repeat;
    background-size: cover;

    .link {
        display: flex;
        gap: 50px;
        background-image: url("../assets/img/dc-logo-bg.png");
        background-size: 700px;
        background-repeat: no-repeat;
        background-position: right;
        padding-block: 40px;




        h3 {
            color: #fff;
            font-size: 26px;
            margin-bottom: 15px;
        }

        ul {
            list-style-type: none;

            li {
                color: #949494;
                margin-bottom: 5px;
                font-size: 18px;
                cursor: pointer;

                &:hover {
                    color: #fff;
                }
            }
        }


    }

}

.contacts {
    background-color: #303030;
    padding-block: 50px;

    .container {

        display: flex;
        justify-content: space-between;
        align-items: center;

        #sign {
            color: #fff;
            padding: 10px;
            border: 2px solid $linkHover;
            text-transform: uppercase;
            font-size: 30px;

            &:hover {
                background-color: $linkHover;
            }
        }

        .social {
            display: flex;
            gap: 20px;

            span {
                text-transform: uppercase;
                color: $linkHover;
                font-size: 30px;
            }

            img {
                color: #fff;
                width: 40px;
            }
        }
    }
}
</style>