<template>
    <div class="header">
    <h1>Vuetastic Real Estate</h1>
    </div>
</template>

<script>
export default {
    name: 'Header',
    props: {
        msg: String
    }
}
</script>

<style scoped>
.header {
    background-color: rgb(133, 197, 199);
    color: white;
    margin: 0%;
    padding: 1%;
}
h1 {
    font-size: 50px;
}
</style>