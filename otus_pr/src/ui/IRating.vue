<template>
    <div class="flex">
        <div class="rating">
            <span v-for="el of 5" :key="el" :class="IsActive(el)"></span>
            <div>{{ props.rating.count }}</div>
        </div>

    </div>
</template>

<script setup>
const props = defineProps({
    rating: {
        type: Object
    }
})
const IsActive = (el) => {
    return (props.rating.rate >= el) ? "active" : ''
}
</script>

<style scoped>
.rating {
    display: flex;
    width: 265px;
    margin: 0 auto;
}

.rating span {
    padding: 0;
    font-size: 32px;
    margin: 0 3px;
    line-height: 1;
    color: lightgrey;
    text-shadow: 1px 1px #bbb;
}

.rating>span:before {
    content: '★';
}

.rating>span.active {
    color: rgb(238, 162, 57);
}
</style>