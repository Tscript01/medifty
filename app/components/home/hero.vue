<template>
    <main class="">
        <div :class="{'pt-16 md:pt-20 lg:pt-32': !scrolled, 'pt-20': scrolled}" class="transition-all duration-300"></div>

        <div id="quote" class="relative h-full py-16 xl:min-h-auto overflow-hidden -mt-20 md:-mt-24 lg:-mt-32">
            <div 
                class="absolute inset-0 bg-cover bg-center bg-no-repeat"
                :style="{backgroundImage: `url('https://images.unsplash.com/photo-1587351021759-3e566b6af7cc?q=80&w=2072')`}"
            >
                <div class="absolute inset-0 bg-[#0A2540] opacity-70"></div>
                <!-- Gradient Overlay -->
                <div class="absolute inset-0 bg-linear-to-r from-[#0A2540] via-[#0A2540]/60 to-transparent"></div>
            </div>
<section class="  relative container ">

            <div class="relative z-10 container   sm:px-6 lg:px-8 py-10 lg:py-32 pt-28">
                <div class="grid grid-cols-1 lg:grid-cols-12 gap-12 items-center">

                    <div class="lg:col-span-7 text-white space-y-6 text-center lg:text-left">
                        <h1 class="text-4xl sm:text-5xl lg:text-6xl font-sora font-extrabold leading-tight">
                            Reliable & Compassionate <br> <span class="text-red-500">Medical Transportation</span>
                        </h1>
                        <p class="text-md sm:text-xl text-gray-300 max-w-xl lg:mx-0 mx-auto">
                            Safe, timely, and professional non-emergency medical transport tailored to your needs, 24/7.
                        </p>
                        <div class="pt-4 hidden md:block">
                            <NuxtLink to="#services" class="px-8 py-3 bg-[#0A9BA3] text-white font-semibold rounded-lg shadow-xl hover:bg-[#0a9ba3ca] transition duration-300 uppercase tracking-wider">
                                Explore Our Services
                            </NuxtLink>
                        </div>
                    </div>

                    <!-- Right Column: Booking/Quote Form -->
                    <div class="lg:col-span-5 hidden lg:block w-full">
                        <div class="bg-white p-6 sm:p-8 rounded-xl shadow-2xl">
                            <h2 class="text-2xl font-bold text-[#0A2540] mb-6 text-center">Get a Free Quote</h2>
                            <form @submit.prevent="handleSubmit" class="space-y-5">
                                
                                <!-- Pickup Location -->
                                <div>
                                    <label for="pickup" class="block text-sm font-medium text-gray-700">Pickup Location</label>
                                    <input type="text" id="pickup" v-model="formData.pickup" required
                                        class="mt-1 block w-full px-4 py-2 border border-gray-300 rounded-md shadow-sm focus:ring-red-500 focus:border-red-500"
                                        placeholder="Enter full address"
                                    >
                                </div>

                                <!-- Dropoff Location -->
                                <div>
                                    <label for="dropoff" class="block text-sm font-medium text-gray-700">Dropoff Location</label>
                                    <input type="text" id="dropoff" v-model="formData.dropoff" required
                                        class="mt-1 block w-full px-4 py-2 border border-gray-300 rounded-md shadow-sm focus:ring-red-500 focus:border-red-500"
                                        placeholder="Enter full address"
                                    >
                                </div>

                                <!-- Date and Time -->
                                <div class="grid grid-cols-2 gap-4">
                                    <div>
                                        <label for="date" class="block text-sm font-medium text-gray-700">Date</label>
                                        <input type="date" id="date" v-model="formData.date" required
                                            class="mt-1 block w-full px-4 py-2 border border-gray-300 rounded-md shadow-sm focus:ring-red-500 focus:border-red-500"
                                        >
                                    </div>
                                    <div>
                                        <label for="time" class="block text-sm font-medium text-gray-700">Time</label>
                                        <input type="time" id="time" v-model="formData.time" required
                                            class="mt-1 block w-full px-4 py-2 border border-gray-300 rounded-md shadow-sm focus:ring-red-500 focus:border-red-500"
                                        >
                                    </div>
                                </div>

                                <!-- Submit Button -->
                                <button type="submit"
                                    class="w-full mt-6 px-4 py-3 bg-[#0A2540] text-white font-semibold rounded-lg shadow-md hover:bg-[#1A3550] transition duration-300"
                                >
                                    Request Booking
                                </button>
                            </form>
                        </div>
                    </div>

                </div>
            </div>
</section>

        </div>

    
 

  

    </main>
</template>

<script setup>
import { ref } from 'vue';

const formData = ref({
    pickup: '',
    dropoff: '',
    date: '',
    time: ''
});

const handleSubmit = () => {
    // In a real application, you would send this data to an API endpoint
    console.log('Booking request:', formData.value);
    alert(`Thank you for your request! We will contact you regarding your trip on ${formData.value.date} at ${formData.value.time}.`);
};

</script>

<style>
/* Ensure Tailwind is configured in your project */
</style>