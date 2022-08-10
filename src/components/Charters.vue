<template>
    <section class="charters__section" id="luxury charters">
        <div class="container">
            <div class="row">
                <Title sectionName="charters" :titleText="title"/>
              
                <div class="charters__cards">
                    <Card v-for="(card, idx) in chartersData" :cardImg="card.img" :cardTitle="card.title" :key="idx"/>
                </div>
                
                <Map/>
            </div>
        </div>            
    </section>
</template>

<script>
import ChartersCardVue from './ChartersCard.vue'
import TitleVue from './Title.vue'
import WorldMapVue from './WorldMap.vue'

export default {
    name: "Charters",
    data() {
        return {
            title: 'luxury charters',
            chartersData: [
                {
                    img: require('@/assets/images/main/piaggio.png'),
                    title: 'piaggio p.180 avanti'
                },
                {
                    img: require('@/assets/images/main/pilatus.png'),
                    title: 'pilatus PC-12'
                },
                {
                    img: require('@/assets/images/main/piper.png'),
                    title: 'piper pa27 aztec'
                },
                {
                    img: require('@/assets/images/main/beech.png'),
                    title: 'beech BE100 King Air'
                }
            ]
        }
    },
    components: {
        Title: TitleVue,
        Card: ChartersCardVue,
        Map: WorldMapVue
    }
}
</script>

<style lang="scss" scoped>
.charters__section {
    width: 100%;
    padding: 30px 0;
    
    .row {
        flex-direction: column;
        align-items: center;
        row-gap: 70px;
    }
    
    .charters__cards {
        width: 100%;
        display: flex;
        justify-content: center;
        gap: 30px;
        flex-wrap: wrap;
    }
}

</style>