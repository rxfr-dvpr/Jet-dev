<template>
    <footer class="footer">
        <div class="container">
            <div class="row">

                <a href="#home" class="footer-logo"><img src="@/assets/images/logoWhite.svg" alt="" class="footer-logo-img"></a>

                <ul class="footer__list">
                    <li v-for="(link, idx) in footerList" :key="idx"><a href="#!" class="footer__link">{{ link }}</a></li>

                    <p class="footer-copyright">© {{ new Date().getFullYear() }} Air. All rights reserved.</p>
                </ul>
            </div>
        </div>
    </footer>
</template>

<script>

export default {
    name: "Footer",
    data() {
        return {
            footerList: [
                'service',
                'about us',
                'news',
                'contact',
            ]
        }
    }
}

</script>

<style lang="scss" scoped>
.footer {
    padding: 50px 0 0;
    background: var(--secondary-color);
    
    .row {
        flex-direction: column;
        align-items: center;
        row-gap: 30px;
    }

    &-logo {
        max-width: 130px;
        width: 100%;
        display: grid;
        place-items: center;

        img {
            width: 100%;
        }
    }

    &__list {
        width: 100%;
        display: flex;
        column-gap: 30px;
        align-items: center;
        padding: 15px 0;
        border-top: 1px solid rgba(255, 255, 255, 0.2);
    }

    &__link {
        font-size: 14px;
        color: rgba(255, 255, 255, 0.7);
        text-transform: uppercase;
        transition: .4s;

        &:hover {
            color: #fff;
        }

    }

    &-copyright {
        font-size: 14px;
        color: rgba(255, 255, 255, 0.7);
        text-transform: capitalize;
        margin-left: auto;
    }
}

@media (max-width: 590px) {
    .footer__list {
        flex-wrap: wrap;
        row-gap: 10px;
        justify-content: center;
        .footer-copyright {
            margin-left: 0;
        }
    }
}

</style>