<template>
  <section class="spesifications__section" id="specification">
    <div class="container">
        <div class="row">
            
            <Title sectionName="specifications" :titleText="title"/>
            
            <div class="specific__cards">
                <Card v-for="(card, idx) in cardData" :key="idx" :cardImg="card.icon" :cardTitle="card.title" :cardText="card.text"/>
                
                <img src="@/assets/images/main/jet-icon.png" alt="" class="flying-jet-img">
            </div>
            
        </div>
    </div>
  </section>
</template>

<script>
import SpecificCardVue from './SpecificCard.vue'
import TitleVue from './Title.vue'

export default {
    name: "Spesifications",
    data() {
        return {
            title: 'private jet performance and specifications',
            cardData: [
                {
                    icon: require("@/assets/images/main/comfort.svg"),
                    title: 'luxury and comfort',
                    text: 'it is a long established fact that a reader will be distracted by the readable'
                },
                {
                    icon: require("@/assets/images/main/security.svg"),
                    title: 'safety and security',
                    text: 'it is a long established fact that a reader will be distracted by the readable'
                },
                {
                    icon: require("@/assets/images/main/schedule.svg"),
                    title: 'personal schedule & booking',
                    text: 'it is a long established fact that a reader will be distracted by the readable'
                },
                {
                    icon: require("@/assets/images/main/captain.svg"),
                    title: 'experienced crew',
                    text: 'it is a long established fact that a reader will be distracted by the readable'
                }
            ]
        }
    },
    components: {
        Title: TitleVue,
        Card: SpecificCardVue
    }
}

</script>

<style lang="scss" scoped>

@media (min-width: 1024px) {
    @keyframes flying {
        from {
            transform: translateY(100%) scale(0.1);
        }
        50% {
            transform: translateY(-500%) scale(1);
        }
        to {
        transform: translateY(-1000%);
        }
    }
}   


.spesifications__section {
    width: 100%;
    padding: 40px 0 30px;
    
    .row {
        flex-direction: column;
        align-items: center;
        row-gap: 60px;
    }
    
    .specific__cards {
        display: flex;
        flex-wrap: wrap;
        gap: 30px;
        justify-content: space-between;
        position: relative;
    }
    
    .flying-jet-img {
        position: absolute;
        top: 40%;
        left: 36.5%;
        max-width: 295px;
        width: 100%;
        z-index: 200222;
        animation: flying 10s linear infinite;
    }
}

@media (max-width: 1070px) {
    .flying-jet-img {
        display: none;    
    }
    
    .specific__cards {
        justify-content: center !important;
    }
}
</style>