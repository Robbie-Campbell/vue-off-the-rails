<template>
  <header class="header">
        <h1>Rab's Playground</h1>
        <div id="nav">
            <router-link active-class="active" to="/" exact>Home</router-link> |
            <router-link active-class="active" to="/about" exact>About</router-link>
            <router-link active-class="active" to="/news" exact>News</router-link>
        </div>
    </header>
</template>

<script>
export default {
    computed: {
    currentRouteName() {
        return this.$route.name;
    }
}
}
</script>

<style scoped>
    .header{
        background: #333;
        color: #fff;
        text-align: center;
        padding:10px;
    }

    .header a{
        color: #fff;
        padding-right: 5px;
    }

    #nav a{
        color: white;
        text-decoration: none;
    }

    .selected{
        font-weight: 700;
    }
    
    .router-link-exact-active{
        font-weight: 700;
    }
</style>