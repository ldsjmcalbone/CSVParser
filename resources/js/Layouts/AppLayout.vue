<script setup>
import { ref } from 'vue';
import { Inertia } from '@inertiajs/inertia';
import { Head, Link } from '@inertiajs/inertia-vue3';
import ApplicationMark from '@/Components/ApplicationMark.vue';
import Banner from '@/Components/Banner.vue';
import Dropdown from '@/Components/Dropdown.vue';
import DropdownLink from '@/Components/DropdownLink.vue';
import NavLink from '@/Components/NavLink.vue';
import ResponsiveNavLink from '@/Components/ResponsiveNavLink.vue';

defineProps({
    title: String,
});

const showingNavigationDropdown = ref(false);
let showSideBar = ref(true);

const toggleSideNav = () => {
    showSideBar.value = !showSideBar.value
}

const switchToTeam = (team) => {
    Inertia.put(route('current-team.update'), {
        team_id: team.id,
    }, {
        preserveState: false,
    });
};

const logout = () => {logout
    Inertia.post(route('logout'));
};
</script>

<template>
    <div>
        <Head :title="title" />

        <Banner />
        <div class="flex h-screen w-screen bg-slate-300">
            <div class="flex flex-col  p-2 font-bold text-center  h-full  min-w-[15rem] bg-white">
                <p class="italic">Ticketing</p>
                <div class="flex p-4 justify-center mt-20 h-30 w-30  bg-white">
                <img class="h-40 w-30 object-cover rounded-md" src="https://w7.pngwing.com/pngs/949/49/png-transparent-check-mark-computer-icons-symbol-green-fruit-miscellaneous-text-logo.png" />
                

                </div>
               
            </div>
                
                <div class="flex flex-col w-screen">
                  <div class="flex justify-end p-1 gap-20 items-center w-full bg-slate-500 h-10 ">
                    <p>not a member? Sign up now</p>
                    
                        <button @click="logout" class="px-4 py-1 text-l text-pink-600 font-semibold rounded-full border border-black hover:text-white hover:bg-pink-600 hover:border-transparent focus:outline-none focus:ring-2 focus:ring-sky-600 focus:ring-offset-2">Log Out</button>
                       
                           

                        

                </div>
                                <div class="flex justify-center p-2 items-center w-full bg-slate-300 h-40">
                                <label class="block">
                                <span class="text-sm font-medium text-slate-700">
                                 NAME
                                </span>
                                <input type="email" name="email" class="mt-1 px-10 py-2 bg-white border shadow-sm border-slate-300 placeholder-slate-400 focus:outline-none focus:border-sky-500 focus:ring-sky-500 block w-full rounded-md sm:text-sm focus:ring-1" placeholder="ex. Michael pogi" />
                                </label>
                                </div>

                                
                            
                            <slot></slot>
            </div>

           
   
                

        </div>

                    
    </div>
</template>
