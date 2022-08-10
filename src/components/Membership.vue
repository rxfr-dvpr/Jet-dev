<template>
    <section class="membership__section" id='membership'>
        <div class="container">
            <div class="row">
                <Title sectionName="membership" :titleText="title"/>

                <div class="membership__cards">
                    <Card v-for="(card, idx) in cardRate" :cardRateData="card" :key="idx"/>
                </div>

                <div class="membership__img-box">
                    <img src="@/assets/images/main/plane.png" alt="" class="moving-jet-img">
                </div>
            </div>
        </div>
    </section>
</template>

<script>
import MembershipCardVue from './MembershipCard.vue'
import TitleVue from './Title.vue'

export default {
    name: "Membership",
    components: {
        Title: TitleVue,
        Card: MembershipCardVue
    },
    data() {
        return {
            title: 'enjoy our membership',
            cardRate: [
                {
                    rateTitle: "popular",
                    rateItems: [
                        'one-time initiation fee $0',
                        'deposit $50k',
                        'pricing / rates dynamic',
                        'priority fleet access yes',
                        'guaranteed fleet access no',
                    ],
                    price: 250
                },
                {
                    rateTitle: "business",
                    rateItems: [
                        'one-time initiation fee $0',
                        'deposit $50k',
                        'pricing / rates dynamic',
                        'priority fleet access yes',
                        'guaranteed fleet access no',
                    ],
                    price: 480
                },
                {
                    rateTitle: "elite",
                    rateItems: [
                        'one-time initiation fee $0',
                        'deposit $50k',
                        'pricing / rates dynamic',
                        'priority fleet access yes',
                        'guaranteed fleet access no',
                    ],
                    price: 680
                }
            ],
        }
    }
}

</script>

<style lang="scss" scoped>

@keyframes movingJet {
    from {
        transform: translateX(100%) scale(0);
    }
    50% {
        transform: translateX(-50%) scale(1);
    }
    to {
        transform: translateX(-200%) scale(1);
    }
}

.membership__section {
    width: 100%;
    padding: 30px 0;

    .container {
        max-width: 1300px !important;
    }
    
    .row {
        flex-direction: column;
        align-items: center;
        row-gap: 105px;
    }

    .membership__cards {
        width: 100%;
        display: flex;
        flex-wrap: wrap;
        gap: 24px;
        justify-content: center;
    }

    .membership__img-box {
        width: 100%;
        position: relative;
        overflow: hidden;
        display: flex;
        justify-content: center;

        .moving-jet-img {
            max-width: 750px;
            width: 100%;
            animation: movingJet 10s linear infinite;
        }
    }
    
}
</style>