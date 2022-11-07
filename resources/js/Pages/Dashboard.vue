<script >
import AppLayout from '@/Layouts/AppLayout.vue';
import { defineComponent } from 'vue';

export default defineComponent({
    name: 'Dashboard',
    components: {
        AppLayout,
       }
})
</script>

<template>
    <AppLayout title="Dashboard">
        <div class="flex flex-col justify-start p-5 items-center w-full bg-slate-300 h-25  g-2">
            <div class="flex item-center justify-center ">
                <p class="font-extrabold text-5xl"> Ticket checker </p>
            
            </div>
               
        
                <div class="flex justify-start p-2 items-center w-full bg-slate-300 h-40">
                    <label class="block">
                    <span class="text-sm font-medium text-slate-700">
                    Issued Ticket
                     </span>
                    <input type="email" name="email" class="mt-2 px-10 py-2 bg-white border shadow-sm border-slate-300 placeholder-slate-400 focus:outline-none focus:border-sky-500 focus:ring-sky-500 block w-full rounded-md sm:text-sm focus:ring-1" placeholder="ex. 001-002-009" />
                    </label>
                </div>

                    <div class="flex justify-start p-2 items-center w-full bg-slate-300 h-40">
                        <label class="block">
                        <span class="text-sm font-medium text-slate-700">
                        Smoke Free
                        </span>
                        <input type="email" name="email" class="mt-2 px-10 py-2 bg-white border shadow-sm border-slate-300 placeholder-slate-400 focus:outline-none focus:border-sky-500 focus:ring-sky-500 block w-full rounded-md sm:text-sm focus:ring-1" placeholder="ex. 001-002-009" />
                        </label>
                     </div>

                        <div class="flex justify-start p-2 items-center w-full bg-slate-300 h-40">
                            <label class="block">
                            <span class="text-sm font-medium text-slate-700">
                            Anti Road Obstruction
                            </span>
                            <input type="email" name="email" class="mt-2 px-10 py-2 bg-white border shadow-sm border-slate-300 placeholder-slate-400 focus:outline-none focus:border-sky-500 focus:ring-sky-500 block w-full rounded-md sm:text-sm focus:ring-1" placeholder="ex. 001-002-009" />
                            </label>
                        </div>

                        
         </div>
      
    </AppLayout>
</template>
