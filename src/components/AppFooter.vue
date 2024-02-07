<script>
export default {
    name: "AppFooter",
    data() {
        return {

            sections: [
                {
                    title: 'DC COMICS',
                    items: [
                        'Characters',
                        'Comics',
                        'Movies',
                        'TV',
                        'Games',
                        'Videos',
                        'News'
                    ]
                },
                {
                    title: 'SHOP',
                    items: [
                        'Shop DC',
                        'Shop DC Collectibles'
                    ]
                },
                {
                    title: 'DC',
                    items: [
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
                    ]
                },
                {
                    title: 'SITES',
                    items: [
                        'DC',
                        'MAD Magazine',
                        'DC Kids',
                        'DC Universe',
                        'DC Power Visa'
                    ]
                }
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
            <div class="link">
                <ul v-for="(item, index) in sections" :key="index">
                    <h3>{{ item.title }}</h3>
                    <li v-for="(element, elementIndex) in item.items" :key="elementIndex">
                        {{ element }}
                    </li>
                </ul>

            </div>
            <div class="bg_Dc">
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
.bg_image {
    background-image: url("../assets/img/footer-bg.jpg");
    background-repeat: no-repeat;
    background-size: cover;
    height: 500px;
    display: flex;
    gap: 400px;
    justify-content: center;
    overflow: hidden;

    .link {
        padding: 20px;
        display: flex;
        gap: 10px;
        flex-direction: column;
        flex-wrap: wrap;

        ul {
            list-style-type: none;
            margin: 12px;

            h3 {
                color: #fff;
                font-size: 26px;
                margin-bottom: 15px;
            }

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

    .bg_Dc {
        background-image: url("../assets/img/dc-logo-bg.png");
        background-size: cover;
        background-position: center;
        height: 700px;
        width: 700px;
        position: relative;
        top: -100px;
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
            border: 2px solid #0282F9;
            text-transform: uppercase;
            font-size: 30px;

            &:hover {
                background-color: #0282F9;
            }
        }

        .social {
            display: flex;
            gap: 20px;

            span {
                text-transform: uppercase;
                color: #0282F9;
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