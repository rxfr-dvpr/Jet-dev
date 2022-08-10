<template>
    <a href="#!" class="choose__link">{{ linkText }}</a>
</template>

<script>
export default {
    name: "Chooose Link",
    props: {
        linkText: {
            type: String,
            default: "choose"
        }
    }
}
</script>

<style lang="scss" scoped>
.choose__link {
    max-width: 350px;
    width: 100%;
    display: flex;
    justify-content: center;
    padding: 12px 0;
    color: var(--third-color);
    font-size: 22px;
    font-weight: 600;
    text-transform: capitalize;
    background: var(--secondary-color);
    border-radius: 12px;
    transition: .4s;
}
</style>