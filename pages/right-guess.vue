<template>
  <div class="d-flex justify-content-center pt-5 pb-5">
    <div id="index" class="mt-5 pb-5">
      <logo />
      <div id="title" class="mt-4">
        You’re correct! <br />
        The right answer is {{ correctAns }}.
      </div>
      <div class="mt-5">
        <right-guess />
      </div>
       <div id="guess" class="mt-4">
        It took you {{ guesses }} guesses.
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Correct',
  data () {
    return {
      correctAns: 0,
      guesses: 0
    }
  },
  created () {
    const isCorrect = localStorage.getItem('correct')
    const guesses = localStorage.getItem('guesses')
    if (!isCorrect && !guesses) {
      this.$router.push('/')
      return false
    }

    this.correctAns = JSON.parse(isCorrect)
    this.guesses = JSON.parse(guesses)

    setTimeout(() => {
      localStorage.removeItem('correct')
      localStorage.removeItem('guesses')
    }, 100)
  }
}
</script>

<style lang="scss">
 #title {
    font-size: 26px;
 }
 #guess {
   font-size: 18px;
 }
</style>
