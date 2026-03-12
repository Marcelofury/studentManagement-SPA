<script setup>

import {ref} from 'vue'
import axios from 'axios'

const name = ref('')
const email = ref('')
const course = ref('')

const submitForm = async()=>{
    if(!name.value || !email.value || !course.value){
        alert('All fields required')
        return
    }

    await axios.post('http://localhost:3000/students', {
        name:name.value,
        email:email.value,
        course:course.value
    })
}

</script>

<template>

    <div>

        <input v-model='name' placeholder='Name'>
        <input v-model='email' placeholder="Email" >
        <input v-model="course" placeholder="Course">

        <button @click="submitForm">Add</button>
    </div>
</template>