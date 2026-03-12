<script setup>
import {ref, onMounted} from 'vue'
import axios from 'axios'

const students = ref([])

const loadStudents = async()=>{

    const res = await axios.get('http://localhost:3000/students')

    students.value = res.data 
}

onMounted(loadStudents)

</script>
<template>
    <ul>
        <li v-for="student in students" :key="student._id">
            {{ student.name }} - {{ student.course }}
        </li>
    </ul>
</template>