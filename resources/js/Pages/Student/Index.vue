<template>
    <div>
        <h1 class="display-1">Welcome to VUE with Laravel</h1>


        <table class="table table-bordered">
            <thead>
                <tr>
                <th>ID</th>
                <th>Name</th>
                <th>Date of Birth</th>
                <th>Address</th>
                <th>Gender</th>
                <th>District</th>
                <th>Languages</th>
                <th>Photo</th>
                <th>Action</th>
            </tr>

            </thead>
          
          <tbody>
            <tr v-for="x in students" :key="x.id">
                <td>{{ x.id }}</td>
                <td>{{ x.name }}</td>
                <td>{{ x.dob }}</td>
                <td>{{ x.address }}</td>
                <td>{{ x.gender }}</td>
                <td>{{ x.district }}</td>
                <td>
                    {{JSON.parse(x.languages).join(', ') }}</td>
                <td><img :src="x.photo" width="100" alt=""></td>
                
                
                <td>
                    <Link :href="route('students.edit', x.id)" class="btn btn-primary">Edit</Link>
                    <button @click="deleteStudent( x.id)" class="btn btn-danger">Delete</button>
                   
                </td>
            </tr>
          </tbody>
        </table>


    </div><br>
    <div>
        <Link :href="route('students.create')" class="btn btn-success">New Entry</Link>
    </div>

    

    
</template>

<!-- <script setup>
        import {Link, useForm, usePage} from '@inertiajs/vue3';

        const {students} = usePage().props
        const form= useForm({});

        const deleteStudent = (id) => {
            // form.delete(`students/${id}`)
            form.delete(route('students.destroy',{id}))

        }
        
       

    </script> -->


<script setup>

import {Link, useForm, usePage} from '@inertiajs/vue3';


const form= useForm({});

const deleteStudent = (id) => {
    // form.delete(`students/${id}`)
    form.delete(route('students.destroy',{id}))

}

defineProps({
  students: {
    type: Array,
    default: () => [],
  },

 
});



</script>

<style scoped>

</style>