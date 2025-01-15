<script setup>
import { useForm } from '@inertiajs/vue3';


const form = useForm({
    name: "",
     dob: "",
     address: "",
      gender: "",
     district: "",
     languages: [],
     photo:""
});

const submit = () => {
  form.post("/students");
};

</script>


<template>
    
    <Head title="Manage Students" />

    <AuthenticatedLayout>
        <template #header>
            <h2 class="font-semibold text-xl text-gray-800 leading-tight">Create student</h2>
        </template>

        <div class="py-12">
            <div class="max-w-7xl mx-auto sm:px-6 lg:px-8">
                <div class="bg-white overflow-hidden shadow-sm sm:rounded-lg">
                    <div class="p-6 text-gray-900">
                       


                       
                        <Link :href="route('students.index')" class="btn btn-success">Back</Link>
                        <form @submit.prevent="submit" class="form" enctype="multipart/form-data">
                            <div class="mb-4 form-group">
                                <label 
                                   
                                    class="block text-gray-700 text-sm font-bold mb-2">
                                    Name:</label>
                                <input 
                                    type="text" 
                                    class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline" 
                                    placeholder="Enter Name" 
                                   
                                    name="name"
                                    v-model="form.name" />

                            </div>

                            <div class="mb-4 form-group">
                                <label 
                                   
                                    class="block text-gray-700 text-sm font-bold mb-2">
                                    Date of Birth:</label>
                                <input 
                                    type="date" 
                                    class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline" 
                                    placeholder="Enter dob" 
                                   
                                    name="dob"
                                    v-model="form.dob" />

                            </div>

                            <div class="mb-4 form-group">
                                <label 
                                  
                                    class="block text-gray-700 text-sm font-bold mb-2">
                                    address:</label>
                                <textarea 
                                    class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline"  name="address"
                                    v-model="form.address" 
                                    placeholder="Enter address"></textarea>
                            </div>

                            <div class="mb-4 form-group">
                                <label 
                                   
                                    class="block text-gray-700 text-sm font-bold mb-2">
                                    gender:  </label>
                                <input 
                                    type="radio" 
                                                                                                                                           
                                    v-model="form.gender" name="gender" value="male" />male 
                                   <input 
                                    type="radio"                                    
                                    v-model="form.gender" name="gender" value="female" />Female 

                            </div>

                           

                            <div class="mb-4 form-group">
                                <label 
                                   
                                    class="block text-gray-700 text-sm font-bold mb-2">
                                    district: </label>

                                    <select name="district"  class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline" v-model="form.district">
                                        <option disabled value>select One</option>
                                        <option value="Dhaka">Dhaka</option>
                                        <option value="Barisal">Barisal</option>
                                        <option value="Khulna">Khulna</option>
                                    </select>

                            </div>

                            <div class="mb-4 form-group">
                                <label 
                                   
                                    class="block text-gray-700 text-sm font-bold mb-2">
                                    language: </label>
                            

                                    <input type="checkbox" name="languages"  value="English" v-model="form.languages">English
                                    <input type="checkbox" name="languages" value="Japanish" v-model="form.languages">Japanish
                                    <input type="checkbox" name="languages" value="Spanish" v-model="form.languages">Spanish

                            </div>


                            <div class="mb-4 form-group">
                                <label 
                                   
                                    class="block text-gray-700 text-sm font-bold mb-2">
                                    Photo:</label>
                                <input 
                                    type="file" 
                                    class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline" @input="form.photo = $event.target.files[0]" 
                                   
                                   
                                  />

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
