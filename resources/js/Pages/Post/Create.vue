<script setup>

import { useForm, Link } from "@inertiajs/vue3";

const form = useForm({
  title: "",
  body: "",
});

const submit = () => {
  form.post("/posts");
};
</script>

<template>
    <Head title="Manage Posts" />

    <AuthenticatedLayout>
        <template #header>
            <h2 class="font-semibold text-xl text-gray-800 leading-tight">Create Post</h2>
        </template>

        <div class="py-12">
            <div class="max-w-7xl mx-auto sm:px-6 lg:px-8">
                <div class="bg-white overflow-hidden shadow-sm sm:rounded-lg">
                    <div class="p-6 text-gray-900">
                       


                       
                        <Link :href="route('posts.index')" class="btn btn-success">Back</Link>
                        <form @submit.prevent="submit" class="form">
                            <div class="mb-4 form-group">
                                <label 
                                    for="title" 
                                    class="block text-gray-700 text-sm font-bold mb-2">
                                    Title:</label>
                                <input 
                                    type="text" 
                                    class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline" 
                                    placeholder="Enter Title" 
                                    id="title"
                                    v-model="form.title" />

                            </div>

                            <div class="mb-4 form-group">
                                <label 
                                    for="body" 
                                    class="block text-gray-700 text-sm font-bold mb-2">
                                    Body:</label>
                                <textarea 
                                    class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline" id="body" 
                                    v-model="form.body" 
                                    placeholder="Enter Body"></textarea>
                            </div>

                            <button type="submit" class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded my-3 text-white">
                                Submit
                            </button>

                        </form>

                    </div>
                </div>
            </div>
        </div>
    </AuthenticatedLayout>
</template>
