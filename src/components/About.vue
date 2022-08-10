<template>
    <section class="about__section" id="private jet">
        <div class="container">
            <div class="row">

                <Title sectionName="about" :titleText="titleText"/>

                <div class="about__content">
                    <img :src="contentImg1" alt="jet" class="about__content-img">

                    <div class="about__content-desc">
                        <h3 class="about__content-title">{{ contentDesc1.title }}</h3>
                        <p class="about__content-text">{{ contentDesc1.text }}</p>
                    </div>
                </div>

                <div class="about__content">
                    <div class="about__content-desc">
                        <h3 class="about__content-title">{{ contentDesc2.title }}</h3>
                        <p class="about__content-text">{{ contentDesc2.text }}</p>
                    </div>

                    <img :src="contentImg2" alt="jet" class="about__content-img">
                </div>

            </div>
        </div>
    </section>
</template>

<script>
import TitleVue from './Title.vue'

export default {
    name: "About",
    components: {
        Title: TitleVue
    },
    data() {
        return {
            titleText: 'Private Jet for Business & Leisure Purposes',
            contentImg1: require('@/assets/images/main/jet.png'),
            contentDesc1: {
                title: "private jet charter",
                text: "it is a long established fact that a reader will be distracted by the readable content of a page when looking at its layout. The point of using Lorem Ipsum is that it has a more-or-less normal distribution of letters, as opposed to using 'Content here, content here', making it look like readable English. Many desktop publishing packages and web page editors"
            },
            contentImg2: require('@/assets/images/main/jet-interior.png'),
            contentDesc2: {
                title: "business jet charter",
                text: "it is a long established fact that a reader will be distracted by the readable content of a page when looking at its layout. The point of using Lorem Ipsum is that it has a more-or-less normal distribution of letters, as opposed to using 'Content here, content here', making it look like readable English. Many desktop publishing packages and web page editors"
            }
        }
    }
}

</script>

<style lang="scss" scoped>
.about__section {
    width: 100%;
    padding-bottom: 40px;
    position: relative;

    &::before {
        content: '';
        max-width: 500px;
        width: 100%;
        height: 450px;
        max-height: 450px;
        background: #E5F4F6;
        border-radius: 0px 50px 50px 0px;
        display: block;
        position: absolute;
        top: 14%;
        left: 0;
        z-index: -1;
    }

    &::after {
        content: '';
        max-width: 500px;
        width: 100%;
        height: 450px;
        max-height: 450px;
        background: #E5F4F6;
        border-radius: 50px 0px 0px 50px;
        display: block;
        position: absolute;
        bottom: 1%;
        right: 0;
        z-index: -1;
    }

    .row {
        row-gap: 140px;
        flex-direction: column;
        align-items: center;
    }

    .about__content {
        width: 100%;
        display: flex;
        justify-content: space-between;
        align-items: center;
        column-gap: 30px;
        row-gap: 20px;

        &-desc {
            max-width: 460px;
            width: 100%;
            display: flex;
            flex-direction: column;
            align-items: flex-start;
            row-gap: 10px;
        }

        &-title {
            text-transform: capitalize;
            color: var(--primary-color);
            font-size: 24px;
            font-weight: 700;
        }

        &-text {
            color: var(--primary-color);
            font-size: 15px;
            letter-spacing: 0.02em;
            color: var(--text-color);
            text-align: justify;

            &::first-letter {
                text-transform: uppercase;
            }
        }

        &-img {
            max-width: 580px;
            width: 100%;
            max-height: 380px;
            height: 100%;
            object-fit: cover;
            border-radius: 30px;
            overflow: hidden;
        }
    }
}

@media (min-width: 1980px) {
    .about__section {
        &::before,&::after {
            display: none;
        }
    }
}

@media (max-width: 1170px) {
    .about__section {
        &::before, &::after {
            display: none !important;
        }
        
        & .row {
            row-gap: 80px !important;
        }
    }
}

@media (max-width: 1140px){}
@media (max-width: 1024px){}
@media (max-width: 992px){}
@media (max-width: 850px){}
@media (max-width: 768px){
    .about__content {
        max-width: max-content;
        flex-direction: column;
    }
}
@media (max-width: 736px){}
@media (max-width: 734px){}
@media (max-width: 684px){}
@media (max-width: 667px){}
@media (max-width: 576px){}
@media (max-width: 480px){}
@media (max-width: 414px){}
@media (max-width: 412px){}
@media (max-width: 375px){}
@media (max-width: 360px){}
@media (max-width: 320px){}


</style>