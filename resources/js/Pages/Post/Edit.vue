<script setup>
import { Link, useForm, usePage } from '@inertiajs/vue3';

const {post} = usePage().props;

const form = useForm({
    title: post.title,
    body: post.body,
})

const update = () => {
    form.put(route('posts.update', post.id))
}

    
    
</script>

<template>
    <div class="container">
        <form @submit.prevent="update">
            <div class="form-group">
                <label for="">Title</label>
                <input type="text" v-model="form.title" class="form-control" name="" id="">

            </div>

            <div class="form-group">
                <label for="">Body</label>
                <input type="text" v-model="form.body" class="form-control" name="" id="">

            </div>
            <button type="submit" class="btn btn-success" name="submit">Update</button>
        </form>

    </div>
</template>



<style scoped>

</style>