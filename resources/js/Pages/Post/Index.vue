<template>
    <div>
        <h1 class="display-1">Welcome to VUE with Laravel</h1>


        <table class="table table-bordered">
            <thead>
                <tr>
                <th>Title</th>
                <th>Details</th>
                <th>Action</th>
            </tr>

            </thead>
          
          <tbody>
            <tr v-for="x in posts" :key="x.id">
                <td>{{ x.title }}</td>
                <td>{{ x.body }}</td>
                <td>
                    <Link :href="route('posts.edit', x.id)" class="btn btn-primary">Edit</Link>
                    <button @click="deletePost( x.id)" class="btn btn-danger">Delete</button>
                   
                </td>
            </tr>
          </tbody>
        </table>


    </div><br>
    <div>
        <Link :href="route('posts.create')" class="btn btn-success">New Entry</Link>
    </div>

    

    
</template>

<!-- <script setup>
        import {Link, useForm, usePage} from '@inertiajs/vue3';

        const {posts} = usePage().props
        const form= useForm({});

        const deletePost = (id) => {
            // form.delete(`posts/${id}`)
            form.delete(route('posts.destroy',{id}))

        }
        
       

    </script> -->


<script setup>

import {Link, useForm, usePage} from '@inertiajs/vue3';


const form= useForm({});

const deletePost = (id) => {
    // form.delete(`posts/${id}`)
    form.delete(route('posts.destroy',{id}))

}

defineProps({
  posts: {
    type: Array,
    default: () => [],
  },
});

</script>

<style scoped>

</style>