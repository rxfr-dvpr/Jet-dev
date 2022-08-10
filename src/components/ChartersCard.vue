<template>
  <div class="charters__card">
    <img :src="cardImg" alt="" class="charters__card-img">
    <p class="charters__card-title">{{ cardTitle }}</p>
  </div>
</template>

<script>

export default {
    name: "Charters Card",
    props: {
        cardImg: {
            type: String,
            required: true
        },
        cardTitle: {
            type: String,
            required: true
        }
    }
}

</script>

<style lang="scss" scoped>
.charters__card {
    min-width: 255px;
    max-width: 255px;
    width: 100%;
    display: flex;
    flex-direction: column;
    align-items: center;
    text-align: center;
    row-gap: 14px;
    background: var(--third-color);
    padding: 14px 12px;
    box-shadow: 0px 30px 84px rgba(19, 10, 46, 0.08), 0px 8px 32px rgba(19, 10, 46, 0.07), 0px 3px 14px rgba(19, 10, 46, 0.03), 0px 1px 3px rgba(19, 10, 46, 0.13);
    border-radius: 12px;
    overflow: hidden;
    
    &-img {
        width: 100%;
        min-height: 189px;
        max-height: 189px;
        height: 100%;
        object-fit: cover;
        border-radius: 12px;
    }
    
    &-title {
        font-size: 16px;
        color: var(--primary-color);
        font-weight: 500;
    }
}
</style>