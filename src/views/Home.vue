<template>
  <div id="home">
      <Navbar />
      <Calculator />
  </div>
</template>

<script>
import Navbar from '../components/Navbar'
import Calculator from '../components/Calculator'

export default {
  name: 'home',
  components: {
    Navbar,
    Calculator
  }
}
</script>