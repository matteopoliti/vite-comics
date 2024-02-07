<script>
export default {
    name: "AppHeader",
    data() {
        return {
            menuItems: [
                {
                    voci: "Characters",
                    status: false
                },

                {
                    voci: "Comics",
                    status: true
                },
                {
                    voci: "Movies",
                    status: false
                },
                {
                    voci: "TV",
                    status: false
                },
                {
                    voci: "Games",
                    status: false
                },
                {
                    voci: "Collectibles",
                    status: false
                },
                {
                    voci: "Video",
                    status: false
                },
                {
                    voci: "Fans",
                    status: false
                },
                {
                    voci: "News",
                    status: false
                },
                {
                    voci: "Shop",
                    status: false
                }
            ],
        }
    }
}



</script>

<template>
    <header>
        <figure>
            <img src="../assets/img/dc-logo.png" alt="Logo DC">
        </figure>
        <nav>

            <ul>
                <li v-for="(item, index) in menuItems" :key="index">
                    <a href="#" :class="(item.status == true) ? 'active' : ''">{{ item.voci }}</a>
                </li>
            </ul>
        </nav>
    </header>
</template>

<style lang="scss" scoped>
header {
    width: 60%;
    margin: 0 auto;
    padding: 20px;
    display: flex;
    align-items: center;
    justify-content: space-between;

    figure {
        width: 100px;
    }

    ul {
        list-style-type: none;
        display: flex;
        gap: 40px;
        font-size: 20px;
        font-weight: 700;
    }

}
</style>
