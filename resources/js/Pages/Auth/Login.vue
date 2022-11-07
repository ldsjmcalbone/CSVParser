
<script >

import { useForm } from '@inertiajs/inertia-vue3';
import InputError from '@/Components/InputError.vue';
export default({
    name: 'Login',
    props: {
        canResetPassword: Boolean,
        status: String,
    },
    components:{
      InputError,
    },
    data(){
        return {
            form: useForm({
                email: '',
                password: '',
                remember: false,
            })
        }
    },
    methods: {
        submit(){
            this.form.transform(data => ({
                ...data,
                remember: this.form.remember ? 'on' : '',
            })).post(route('login'), {
                onFinish: () => this.form.reset('password'),
            });
        }
    }
})
</script>

<template>
    <div class="bg-slate-500 text-black">
  <div class="min-h-screen bg-slate-500 flex justify-center items-center">
    <div class="p-8 flex-1">
      <div class="w-80 bg-white rounded-3xl mx-auto overflow-hidden shadow-xl">
        <div class="relative h-48 bg-blue-200 rounded-bl-4xl">
          
        </div>
        <div class="px-10 pt-4 pb-8 bg-white rounded-tr-4xl">
          <InputError class="mt-2" :message="form.errors.email" />
          <h1 class="text-2xl font-semibold text-gray-900">HELLO! PLEASE SIGN IN!</h1>
          
            <div class="relative">
              <input v-model="form.email" id="email" name="email" type="text" class="peer h-10 w-full border-b-2 border-gray-300 text-gray-900 placeholder-transparent focus:outline-none focus:border-rose-600" placeholder="john@doe.com" />
              <label for="email" class="absolute left-0 -top-3.5 text-gray-600 text-sm transition-all peer-placeholder-shown:text-base peer-placeholder-shown:text-gray-400 peer-placeholder-shown:top-2 peer-focus:-top-3.5 peer-focus:text-gray-600 peer-focus:text-sm">Email address</label>
            </div>
            <div class="mt-10 relative">
              <input v-model="form.password" id="password" type="password" name="password" class="peer h-10 w-full border-b-2 border-gray-300 text-gray-900 placeholder-transparent focus:outline-none focus:border-rose-600" placeholder="Password" />
              <label for="password" class="absolute left-0 -top-3.5 text-gray-600 text-sm transition-all peer-placeholder-shown:text-base peer-placeholder-shown:text-gray-400 peer-placeholder-shown:top-2 peer-focus:-top-3.5 peer-focus:text-gray-600 peer-focus:text-sm">Password</label>
            </div>


            <div @click="submit" class="mt-20 px-4 py-2 rounded bg-green-800 hover:bg-rose-400 text-white font-semibold text-center block w-full focus:outline-none focus:ring focus:ring-offset-2 focus:ring-rose-500 focus:ring-opacity-80 cursor-pointer">
                Sign In
            </div>

    
         
          <a href="#" class="mt-4 block text-sm text-center font-medium text-green-600 hover:underline focus:outline-none focus:ring-2 focus:ring-rose-500"> Forgot your password? </a>
          
        </div>
      </div>
    </div>
  </div>
</div>
</template>
