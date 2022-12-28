<template>
    <div class="w-full h-screen text-white relative">
        <div class="fixed top-[60%] sm:top-[60%] md:top-[60%] lg:top-[65%] xl:top-[72%] 2xl:top-[78%] left-[28%] sm:left-[35%]">
            <div @mouseover="isOpenBio=true" @mouseleave="isOpenBio=false" class="hidden md:flex animate-bounce transition-all hover:bg-orange-100 bg-gray-200 md:w-14 md:h-14 flex-col justify-center items-center rounded-full">
                <span class="text-lg absolute pb-20">BIO</span>
                <img src="/icons/double-arrow-dot-orange.svg" alt="arrow icon" class="h-5 rotate-90 pl-1">
            </div>
            <button @click="OpenBio( )" :class="isOpenBio || isOpenTraits ? 'hidden' : '' " class="md:hidden animate-bounce transition-all hover:bg-orange-100 bg-gray-200 w-12 h-12 flex flex-col justify-center items-center rounded-full">
                <span class="text-lg absolute pb-20">BIO</span>
                <img src="/icons/double-arrow-dot-orange.svg" alt="arrow icon" class="h-4 rotate-90 pl-1">
            </button>
            <div v-if="isOpenBio" class="fixed left-0 z-[9] lg:left-12 top-12 p-6 rounded-xl shadow-xl bg-gray-200">  
                <button @click="isOpenBio=false" class="md:hidden absolute top-3 right-3 bg-black w-6 h-6 flex items-center justify-center rounded-full">
                    <img src="/icons/x-white.svg" alt="x icon" class="">
                </button>
                <p class="text-md md:text-xl text-black ">
                    Hey, how are you? 
                    <br><br>
                    My name is Ricardo, I'm {{ age }} and currently studing Analysis and Systems Development. 
                    <br>
                    I started an <strong>internship in June/2022</strong> where my focus is on Front-End development.
                    <br>
                    I learned how to build websites with <strong>VueJS</strong>, <strong>Astro</strong> and <strong>Tailwind</strong>, which is what I'm using in this page.
                    <br><br>
                    At the moment, I'm working in a WebApp that will be used in business environment. 
                    <br>
                    Mainly to make sales, register customers, products, and get data for BI.
                </p>
            </div>
        </div>

        <div class="fixed top-[42%] md:top-[40%] 2xl:top-[38%] left-[53%] 2xl:left-[55%]">
            <div @mouseover="isOpenTraits=true" @mouseleave="isOpenTraits=false" class="hidden md:flex animate-bounce transition-all hover:bg-orange-100 bg-gray-200 md:w-14 md:h-14 flex-col justify-center items-center rounded-full">
                <span class="text-lg absolute pb-20">TRAITS</span>
                <img src="/icons/double-arrow-dot-orange.svg" alt="arrow icon" class="h-5 rotate-90 pl-1">
            </div>
            <div @click="OpenTraits( )" :class="isOpenBio || isOpenTraits ? 'hidden' : '' " class="md:hidden relative z-0 animate-bounce transition-all hover:bg-orange-100 bg-gray-200 w-12 h-12 flex flex-col justify-center items-center rounded-full">
                <span class="text-lg absolute pb-20 ">TRAITS</span>
                <img src="/icons/double-arrow-dot-orange.svg" alt="arrow icon" class="h-4 rotate-90 pl-1">
            </div>
            <div v-if="isOpenTraits" class="text-md md:text-xl text-black fixed md:mx-12 left-0 top-12 md:top-12 p-6 rounded-xl shadow-xl bg-gray-200">  
                <button @click="isOpenTraits=false" class="md:hidden absolute top-3 right-3 bg-black w-6 h-6 flex items-center justify-center rounded-full">
                    <img src="/icons/x-white.svg" alt="x icon" class="">
                </button>
                <p class="">
                    I like to learn new things, so being abble to work in different projects gives me excitment.  
                    <br> <br>      
                    I usually learn on my own, by trying and error, searching in google, and giving a creative solution to problems.
                    <br> <br>
                    The ability to learn and use that knowledge helped me when I started my coffeeshop, back in 2016. 
                    <br>
                    Since it was a small business, I had to learn so many different things at the same time, including how to be a good leader.
                    <br>
                    It wasn't easy but it gave me a broader vision of how to deal with conflictant relations and stablish a good working environment.
                    <br> <br>
                    Today, I would describe myself as responsible and focused. 
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
            isOpenBio: false,
            isOpenTraits: false,
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
        },
        OpenBio ( )
        {
            this.isOpenBio = !this.isOpenBio
            this.isOpenTraits = false
        },
        OpenTraits ( )
        {
            this.isOpenTraits = !this.isOpenTraits
            this.isOpenBio = false
        }
    },
    mounted ( )
    {
        this.GetAge (  )
    }
}
</script>