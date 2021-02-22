<template>
    <div id="about">
        <Navbar />
        <div class="container">
            <h1>Practicing Vue</h1>
            <p>Lorem ipsum, dolor sit amet consectetur adipisicing elit. Labore voluptatibus illum nulla ipsam dolorum quam totam quo odit sint placeat quisquam, fuga animi libero. Optio eos sapiente repudiandae libero tempora?</p>
        </div>
    </div>
</template>

<script>
import Navbar from '../components/Navbar'

export default {
  name: 'about',
  components: {
    Navbar
  }
}
</script>

<style>
</style>