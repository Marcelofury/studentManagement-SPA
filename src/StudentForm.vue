<script setup>

import {ref} from 'vue'
import axios from 'axios'

const name = ref('')
const email = ref('')
const course = ref('')

</script>

<template>

    <div>

        <input v-model='name' placeholder='Name'>
        <input v-model='email' placeholder="Email" >
        <input v-model="course" placeholder="Course">

        <button @click="submitForm">Add</button>
    </div>
</template>