<template>
    <h2 :class="`${sectionName}__section-title`">{{ titleText }}</h2>
</template>

<script>

export default {
    name: 'Title',
    props: {
        titleText: {
            type: String,
            default: 'title'
        },
        sectionName: {
            type: String,
            default: 'section'
        }
    }
}

</script>

<style lang="scss" scoped>
h2 {
    font-size: calc(30px + 6 * (100vw / 1920));
    text-transform: capitalize;
    color: var(--primary-color);
    text-align: center;
    position: relative;
    
    &::after {
        content: '';
        width: 40px;
        height: 40px;
        border-radius: 50%;
        background: rgba(21, 21, 21, 0.2);
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);   
        z-index: -1; 
    }
}

@media (max-width: 840px) {
    h2::after {
        display: none;
    }
}

@media (max-width: 320px) {
    h2 {
        font-size: calc(30px + (6 + 6 * 0.7) * ((100vw - 320px)/ 1920));
    }
}
</style>