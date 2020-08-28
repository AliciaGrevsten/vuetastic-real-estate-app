<template>
    <div class="header">
        <img src="../assets/images/Vuetastic-Real-Estate-Icon.png">
    <h1>VUEtastic Real Estate</h1>
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
    margin: 0%;
    padding: 1%;
    border-bottom: 4px double rgb(22, 52, 80);
}
h1 {
    font-size: 50px;
    color: rgb(22, 52, 80);
    padding: 0%;
    margin: 0%;
}
img {
    height: 100px;
}
</style>