<!-- ในไฟล์ src/components/StudentDashboard.vue -->
<template>
  <div>
    <input type="text" v-model="checkinId" placeholder="Enter Check-In ID">
    <button @click="checkIn">Check In</button>
    <div v-for="question in questions" :key="question.id">
      <p>{{ question.text }}</p>
      <input type="text" v-model="answers[question.id]" placeholder="Your Answer">
      <button @click="answerQuestion(question.id)">Submit Answer</button>
    </div>
  </div>
</template>

<script>
import firebase from 'firebase/app'
import 'firebase/firestore'

export default {
  data() {
    return {
      checkinId: '',
      questions: [],
      answers: {}
    }
  },
  methods: {
    checkIn() {
      // โค้ดสำหรับเช็คชื่อนักเรียน
    },
    answerQuestion(questionId) {
      // โค้ดสำหรับส่งคำตอบของนักเรียน
    },
    loadQuestions() {
      // โค้ดสำหรับโหลดคำถามจาก Firestore
    }
  },
  mounted() {
    this.loadQuestions()
  }
}
</script>
