<template>
  <div class="d-flex justify-content-center pt-5 pb-5">
    <h1 v-if="!total && !possibleGuesses">
      Loading.......
    </h1>
    <div v-if="total && possibleGuesses" id="index" class="mt-5 pb-5">
      <logo />
      <div id="title" class="mt-4">
        Guess the secret <br>
        prime number!
      </div>
      <div id="desc" class="mt-4">
        The secret number is a prime number under 100.<br>
        You have to sum up 4 numbers to reach the secret<br>
        number. For example, if the number is 11, the four <br>
        clues could be 4, 2, 4, 1.
      </div>
      <div id="guess-the-number" class="mt-3">
        Guess the number
      </div>
      <form @submit.prevent="handleGuessAnswer">
        <div class="col-lg-12 d-flex mt-2">
          <div class="col-lg-6">
            <input v-model="guessNumber" type="number" :class="[wrongAns ? 'form-control error':'form-control']">
          </div>
          <div class="col-lg-4 px-2">
            <button type="submit" class="btn btn-primary">
              CHECK
            </button>
          </div>
        </div>
      </form>
      <div v-show="wrongAns" id="error-text">
        Wrong guess
      </div>
      <div class="d-flex col-lg-12 collapes">
        <div v-for="i in possibleGuesses" :key="i">
          <div class="px-1">
            <option-box :possible-sum="i" />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import errorMessages from '@/helper/error'
export default {
  name: 'Questionaire',
  data () {
    return {
      wrongAns: false,
      guessNumber: null,
      total: null,
      possibleGuesses: [],
      guesses: 0
    }
  },
  async created () {
    try {
      const { data: { result: { total, possibleSums } } } = await this.$axios.get('/getsecret')
      this.total = total
      this.possibleGuesses = possibleSums
    } catch (error) {
      alert(errorMessages.serverError)
      console.log(error)
    }
  },
  methods: {
    handleGuessAnswer () {
      if (!Number(this.guessNumber)) {
        alert(errorMessages.emptyInput)
      } else if (Number(this.guessNumber) !== this.total) {
        this.wrongAns = true
        this.guesses += 1
        setTimeout(() => {
          this.wrongAns = false
        }, 2000)
      } else {
        localStorage.setItem('guesses', JSON.stringify(this.guesses))
        localStorage.setItem('correct', JSON.stringify(this.total))
        this.$router.push('/right-guess')
      }
    }
  }
}
</script>

<style lang="scss" scoped>
#index {
    width: 100%;
    padding-left: 10px;
  @media (min-width: 800px) {
    padding-left: 0;
    width: 30%;
  }
}
/* Chrome, Safari, Edge, Opera */
input::-webkit-outer-spin-button,
input::-webkit-inner-spin-button {
  -webkit-appearance: none;
  margin: 0;
}

/* Firefox */
input[type="number"] {
  -moz-appearance: textfield;
}
#title {
  font-style: normal;
  font-weight: 300;
  font-size: 30px;
  line-height: 30px;
  color: #000000;
}

#desc {
  font-style: italic;
  font-weight: normal;
  font-size: 16px;
  line-height: 19px;
  color: #000000;
}

#guess-the-number {
  font-style: normal;
  font-weight: bold;
  font-size: 18px;
  line-height: 21px;
  color: #000000;
}

.collapes {
  flex-wrap: wrap;
  margin-left: -4px;
}

.error {
  border: 2px solid red;
}

#error-text {
  font-style: italic;
  font-weight: normal;
  font-size: 16px;
  line-height: 19px;
  color: #FF0202;
  font-style: italic;
}
</style>
