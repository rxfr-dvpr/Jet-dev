<template>
  <div class="membership__card">
    <h3 class="membership__card-title">{{ cardRateData.rateTitle }}</h3>
    <p class="membership__card-subtitle">what you'll get</p>

    <ul class="membership__card-list">
        <li class="membership__card-item" v-for="(item, idx) in cardRateData.rateItems" :key="idx"><i class="fas fa-check-circle" :class="idx == 0 || idx == 1 || idx == 2 ? 'active' : ''"></i> {{ item }}</li>
    </ul>

    <p class="membership__card-price"><span class="price-num">${{ cardRateData.price }}</span>/month</p>

    <ChooseLink linkText="choose link"/>

  </div>
</template>

<script>
import chooseLinkVue from './chooseLink.vue'

export default {
    name: "Membership Card",
    props: {
        cardTitle: {
            type: String,
            default: "title"
        },
        cardRateData: {
            type: Object,
            default: {
                rateTitle: "",
                rateItems: [],
                price: 0
            }
        }
    },
    components: {
        ChooseLink: chooseLinkVue
    }
}

</script>

<style lang="scss" scoped>
.membership__card {
    max-width: 400px;
    width: 100%;
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    padding: 25px;
    background: #F5F5F5;
    border-radius: 20px;
    cursor: pointer;
    transition: .4s ease-in-out;

    &:first-of-type {
        border-radius: 20px 0px 0px 20px;
    }

    &:last-of-type {
        border-radius: 0px 20px 20px 0px;
    }

    &-title {
        text-transform: capitalize;
        font-size: 32px;
        color: var(--primary-color);
        font-weight: 700;
        transition: .4s;
    }

    &-subtitle {
        font-size: 20px;
        color: #A9A9AA;
        text-transform: capitalize;
        margin: 10px 0 15px;
    }

    &-list {
        width: 100%;
        display: flex;
        flex-direction: column;
        align-items: flex-start;
        row-gap: 10px;
        padding-bottom: 15px;
        margin-bottom: 65px;
        border-bottom: 1px dashed #A9A9AA;
    }

    &-item {
        text-transform: capitalize;
        display: flex;
        column-gap: 10px;
        align-items: center;
        font-weight: 500;
        color: var(--primary-color);
        font-size: 16px;
        transition: .4s;

        & > i.active {
            color: green;
        }
    }

    .membership__card-price {
        color: var(--primary-color);
        font-size: 18px;
        font-weight: 500;
        margin-bottom: 24px;
        transition: .4s;

        & > .price-num {
            font-size: 32px;
            font-weight: 700;
        }
    }
}

@media (min-width: 1300px) {
    .membership__card {
        &:hover {
            transform: translateY(-40px);
            background: var(--secondary-color);

            .choose__link {
                background: var(--third-color);
                color: var(--primary-color);
            }

            .membership__card-item {
                color: var(--third-color);
            }

            .membership__card-price {
                color: var(--third-color);
            }

            .membership__card-title {
                color: var(--third-color);
            }
        }
    }
}
</style>