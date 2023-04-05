<template>
  <div>
    <h1>{{ question }}</h1>
    <div v-for="(option, index) in options" :key="index">
      <input type="radio" :id="'option'+index" :value="option" v-model="selectedOption">
      <label :for="'option'+index">{{ option }}</label>
    </div>
    <button @click="checkAnswer">Submit</button>
    <button v-if="answered" @click="nextQuestion">Next Question</button>
    <div v-if="answered">
      <h2>CORRECT!</h2>
      <h3>{{ info }}</h3>
      <h3><a :href="additional" target="_blank">Additional Information</a></h3>
    </div>
  </div>
</template>

<script>
export default {
  name: 'QuizQuestions',
  data: () => ({
    questions: [
      {
        question: "Who is in charge of the executive branch?",
        options: ["The president", "The chief justice of the Supreme Court", "The vice president", "The secretary of the treasury"],
        answer: "The president",
        info: "The executive branch (the president, vice president, cabinet, and most federal agencies) carries out laws. The legislative (Congress) and judicial (Supreme Court and other courts) are the other branches of the US government.",
        additional: "https://www.whitehouse.gov/about-the-white-house/our-government/the-executive-branch/"
      },
      {
        question: "What are the two parts of the US Congress?",
        options: ["The Senate and House of Representatives", "The Senate and Supreme Court", "The House of Representatives and Supreme Court", "The president and the House of Representatives"],
        answer: "The Senate and House of Representatives",
        info: "The United States Congress is the legislature of the federal government of the United States. It is bicameral, composed of a lower body, the House of Representatives, and an upper body, the Senate.",
        additional: "https://www.youtube.com/watch?v=irIuYLzj_Qc"
      },
      {
        question: "How many US senators are there?",
        options: ["9", "50", "100", "435"],
        answer: "100",
        info: "The Senate has 100 members, two from each state, who are elected for six-year terms. Every two years, one-third of the Senate is up for reelection.",
        additional: "https://www.britannica.com/topic/Senate-United-States-government"
      }
    ],
    currentQuestionIndex: 0,
    selectedOption: null,
    answered: false
  }),
  computed: {
    question() {
      return this.questions[this.currentQuestionIndex].question;
    },
    options() {
      return this.questions[this.currentQuestionIndex].options;
    },
    answer() {
      return this.questions[this.currentQuestionIndex].answer;
    },
    info() {
      return this.questions[this.currentQuestionIndex].info;
    },
    additional() {
      return this.questions[this.currentQuestionIndex].additional;
    }
  },
  methods: {
    checkAnswer() {
      if (this.selectedOption === this.answer) {
        this.answered = true;
      } else {
        this.answered = false;
        alert('Incorrect!');
      }
    },
    nextQuestion() {
      if (this.currentQuestionIndex < this.questions.length - 1) {
        this.currentQuestionIndex++;
        this.selectedOption = null;
        this.answered = false;
      } else {
        alert('Quiz completed!');
      }
    }
  }
};
</script>
``
