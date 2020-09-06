<template>
    <div>
    <div v-bind:key="name.id" v-for="name in names">
        <h4 v-on:del-name="$emit('del-name', name.id)">{{ name.name }}
            <button class="del" @click="$emit('del-name', name.id)">X</button>
        </h4>
    </div>
    </div>
</template>

<script>
export default {
    name: "Names",
    props: ["names"]
}
</script>

<style scoped>

</style>