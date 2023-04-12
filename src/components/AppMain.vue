<script>
import ServicesItem from './ServicesItem.vue';
import ShowCaseItem from './ShowCaseItem.vue';
import BlogItem from './BlogItem.vue';
export default {
    data() {
        return {

        };
    },

    components: {
        ServicesItem,
        ShowCaseItem,
        BlogItem,
    }
}
</script>

<template>
    <main>
        <ServicesItem></ServicesItem>
        <ShowCaseItem></ShowCaseItem>
        <BlogItem></BlogItem>
    </main>
</template>

<style lang="scss" scoped></style>