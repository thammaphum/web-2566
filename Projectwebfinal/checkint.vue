<!-- ในไฟล์ src/components/CheckInTeacher.vue -->
<template>
  <div>
    <button @click="checkIn">Check In</button>
    <div v-for="checkin in checkins" :key="checkin.id">
      <p>Subject: {{ checkin.subject }}</p>
      <p>Room: {{ checkin.room }}</p>
      <p>Date: {{ checkin.class_date }}</p>
      <button @click="viewStudents(checkin.id)">View Students</button>
    </div>
  </div>
</template>

<script>
import firebase from 'firebase/app'
import 'firebase/firestore'

export default {
  data() {
    return {
      checkins: []
    }
  },
  mounted() {
    this.loadCheckIns()
  },
  methods: {
    loadCheckIns() {
      firebase.firestore().collection('checkin').get()
        .then(snapshot => {
          snapshot.forEach(doc => {
            this.checkins.push(doc.data())
          })
        })
    },
    checkIn() {
      // โค้ดสำหรับเพิ่มการเช็คชื่อใน Firestore
    },
    viewStudents(checkinId) {
      // โค้ดสำหรับดึงรายชื่อนักเรียนที่เช็คชื่อในการเช็คชื่อนี้
    }
  }
}
</script>
