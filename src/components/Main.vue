<template>
    <main class="main">
        <About/>
        <Spesifications/>
        <Charters/>
        <Membership/>
    </main>
</template>

<script>
import AboutVue from './About.vue'
import ChartersVue from './Charters.vue'
import MembershipVue from './Membership.vue'
import SpesificationsVue from './Spesifications.vue'

export default {
    name: "Main",
    components: {
        About: AboutVue,
        Spesifications: SpesificationsVue,
        Charters: ChartersVue,
        Membership: MembershipVue
    }
}

</script>

<style lang="scss" scoped>
.main {
    width: 100%;
    display: flex;
    flex-direction: column;
    align-items: center;
}
</style>