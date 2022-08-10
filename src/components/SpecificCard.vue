<template>
    <div class="specific__card">
        <img :src="cardImg" alt="jet icon" class="specific__card-icon">
        <h3 class="specific__card-title">{{ cardTitle }}</h3>
        <p class="specific__card-text">{{ cardText }}</p>
    </div>
</template>

<script>
export default {
    name: "Specific Card",
    props: {
        cardImg: {
            type: String,
            required: true
        },
        cardTitle: {
            type: String,
            required: true,
            default: 'title'
        },
        cardText: {
            type: String,
            required: true,
            default: "Lorem ipsum, dolor sit amet consectetur adipisicing elit. Nam, earum?"
        }
    }
}
</script>

<style lang="scss" scoped>
.specific__card {
    max-width: 370px;
    min-width: 250px;
    width: 100%;
    display: flex;
    flex-direction: column;
    align-items: center;
    text-align: center;
    row-gap: 12px;
    padding: 40px 50px 50px;
    background: var(--third-color);
    box-shadow: 0px 30px 84px rgba(19, 10, 46, 0.08), 0px 8px 32px rgba(19, 10, 46, 0.07), 0px 3px 14px rgba(19, 10, 46, 0.03), 0px 1px 3px rgba(19, 10, 46, 0.13);
    border-radius: 12px;
    
    &-icon {
        max-width: 55px;
        min-width: 55px;
        max-height: 55px;
        min-width: 55px;   
        width: 100%;
        height: 100%;
        object-fit: cover;
    }
    
    &-title {
        width: 100%;
        font-size: 18px;
        font-weight: 600;
        color: var(--primary-color);
        text-transform: capitalize;
        overflow: hidden;
        white-space: nowrap;
        text-overflow: ellipsis;
    }
    
    &-text {
        font-size: 16px;
        color: var(--text-color);
        letter-spacing: 0.02em;
        -webkit-line-clamp: 3;
        -webkit-box-orient: vertical;
        display: -webkit-box;
        overflow: hidden;
        
        &:first-letter {
            color: red;
        }
    }
}

@media (max-width: 425px) {
    .specific__card {
        padding: 20px 25px !important;
    }
}

@media (max-width: 345px) {
    .specific__card {
        padding: 20px 15px !important;
    }
}

</style>