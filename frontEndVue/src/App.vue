<template>
  <h1>The Citizenship exam contains 100 questions. Prepare for your upcoming exam! </h1>
  <section class="quiz-container">
    <QuizQuestions />
  </section>
</template>

<script>
import QuizQuestions from './components/QuizQuestions.vue'

export default {
  name: 'App',
  components: {
    QuizQuestions
  }
}
</script>

<style>

  body {
    font-family: Arial, sans-serif;
  }

  .quiz-container {
    max-width: 600px;
    margin: 0 auto;
    padding: 20px;
    border: 1px solid #ddd;
    border-radius: 5px;
    box-shadow: 0 2px 5px rgba(0,0,0,0.1);
    background-color: #fff;
  }

  h1 {
    font-size: 24px;
    font-weight: bold;
    margin-bottom: 20px;
  }

  label {
    margin-left: 10px;
  }

  input[type=radio] {
    margin-right: 10px;
  }

  button {
    display: block;
    margin: 20px auto 0;
    padding: 10px 20px;
    border-radius: 5px;
    background-color: #007aff;
    color: #fff;
    font-size: 16px;
    font-weight: bold;
    cursor: pointer;
    border: none;
  }

  button:hover {
    background-color: #0062cc;
  }

  .feedback {
    margin-top: 20px;
    padding: 20px;
    border-radius: 5px;
    background-color: #f8f8f8;
    border: 1px solid #ddd;
  }

  .feedback h3 {
    font-size: 18px;
    margin-bottom: 10px;
  }

  .feedback p {
    font-size: 14px;
    margin-bottom: 0;
  }
</style>

