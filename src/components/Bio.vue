<template>
    <div class="w-full h-screen text-white relative">
        <div class="fixed top-[60%] sm:top-[60%] md:top-[60%] lg:top-[65%] xl:top-[72%] 2xl:top-[78%] left-[28%] sm:left-[35%]">
            <div @mouseover="isOpen=true" @mouseleave="isOpen=false" class="hidden md:flex animate-bounce transition-all hover:bg-orange-100 bg-gray-200 md:w-14 md:h-14 flex-col justify-center items-center rounded-full">
                <img src="/icons/double-arrow-dot-orange.svg" alt="arrow icon" class="h-5 rotate-90 pl-1">
            </div>
            <div @click="OpenBio( )" class="md:hidden animate-bounce transition-all hover:bg-orange-100 bg-gray-200 w-12 h-12 flex flex-col justify-center items-center rounded-full">
                <img src="/icons/double-arrow-dot-orange.svg" alt="arrow icon" class="h-4 rotate-90 pl-1">
            </div>
            <div v-if="isOpen" class="text-md md:text-xl text-black fixed md:left-12 md:top-12 p-6 rounded-xl shadow-xl bg-gray-200">  
                <p class="">
                    Hey, how are you? 
                    <br><br>
                    My name is Ricardo, I'm {{ age }} and currently studing Analysis and Systems Development. 
                    <br>
                    I started an <strong>internship in June/2022</strong> where my focus is on Front-End development.
                    <br>
                    I learned how to build websites with <strong>VueJS</strong>, <strong>Astro</strong> and <strong>Tailwind</strong>, which is what I'm using in this page.
                    <br><br>
                    At the moment, I'm working in a WebApp that will be used in business enviroment. 
                    <br>
                    Mainly to make sales, register customers, products, and get data for BI.
                </p>
            </div>
        </div>
    </div>

</template>

<script>
export default 
{
    data ( )
    {
        return {
            isOpen: false,
            age: 0,
            
        }
    },
    methods:
    {
        GetAge (  )
        {
            let dob = new Date ( 1989, 4, 10 )
            let diff = Date.now ( ) - dob.getTime ( )
            this.age = new Date ( diff )
            this.age = Math.abs( this.age.getUTCFullYear( ) - 1970 )
        }
    },
    mounted ( )
    {
        this.GetAge (  )
    }
}
</script>