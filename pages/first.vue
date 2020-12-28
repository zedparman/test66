<template>
    <div  class="container">
        <h1>Hello</h1>
        <ul>
         <li v-for="s in students" :key="s.family">
         {{ s.nam }}
         </li>
        </ul>
    </div>
</template>

<script>
import axios from 'axios'
export default {
    data(){
        return{
            students: []
        }
    },
    methods: {
        async studentsList(){
            try{
                let response = await axios.get('http://test3.egpayesh.ir/students')
                this.students = response.data
                console.log(response)
            } catch(error) {
                console.log(error)
            }
        }   
    },
    mounted(){
      this.studentsList()
    }
}
</script>

<style>

</style>