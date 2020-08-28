<template>
    <div class="header">
        <img
        src="../assets/images/Vuetastic-Real-Estate-Icon.png"
          alt="Picture of listing"
        />
    <h1><strong>VUE</strong>tastic Real Estate</h1>

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
    padding: 2%;
}
img {
    height: 100px;
    float: left;
}
h1 {
    color: rgb(58, 82, 104);
}
</style>