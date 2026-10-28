<script>
export default {
    name: 'Contact'
}
</script>

<template>
    <section class="text-gray-600 bg-black body-font relative w-full min-h-screen">

        <!-- Main Container -->
        <div class="w-full max-w-7xl mx-auto
            px-4 sm:px-6 lg:px-8
            py-10 sm:py-14 lg:py-24
            flex flex-col lg:flex-row
            gap-6 sm:gap-8 lg:gap-10
            items-stretch">

            <!-- MAP AND CONTACT INFORMATION -->
            <div class="w-full lg:w-2/3
                min-w-0
                bg-gray-300
                rounded-lg overflow-hidden
                p-4 sm:p-6 lg:p-10
                flex flex-col
                items-stretch justify-end
                relative
                min-h-[420px] sm:min-h-[450px]
                lg:min-h-[550px]">

                <!-- Google Maps -->
                <iframe class="absolute inset-0 w-full h-full" frameborder="0" title="Silingan Location Map"
                    marginheight="0" marginwidth="0" scrolling="no" loading="lazy" allowfullscreen
                    src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d5391764.973424185!2d119.62420584757544!3d14.536088740114211!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x324053215f87de63%3A0x784790ef7a29da57!2sPhilippines!5e0!3m2!1sen!2sph!4v1792717421857!5m2!1sen!2sph"
                    style="filter: grayscale(1) contrast(1.2) opacity(0.4);"></iframe>

                <!-- Address, Email and Phone -->
                <div class="bg-white relative z-10
                    w-full
                    flex flex-col sm:flex-row
                    flex-wrap
                    py-5 sm:py-6
                    rounded-lg shadow-md
                    gap-y-5">

                    <!-- Address -->
                    <div class="w-full sm:w-1/2 px-5 sm:px-6">
                        <h2 class="font-semibold text-gray-900
                            tracking-widest text-xs">
                            ADDRESS
                        </h2>

                        <p class="mt-2 leading-relaxed text-sm sm:text-base">
                            Visit your nearest Silingan branch today and enjoy
                            fast, reliable, and affordable shipping for all
                            your cravings
                        </p>
                    </div>

                    <!-- Email and Phone -->
                    <div class="w-full sm:w-1/2 px-5 sm:px-6">

                        <h2 class="font-semibold text-gray-900
                            tracking-widest text-xs">
                            EMAIL
                        </h2>

                        <a href="mailto:silingan@gmail.com" class="text-red-500 leading-relaxed
                            break-words hover:text-red-600">
                            silingan@gmail.com
                        </a>

                        <h2 class="font-semibold text-gray-900
                            tracking-widest text-xs mt-4">
                            PHONE
                        </h2>

                        <a href="tel:1234567890" class="leading-relaxed text-gray-600
                            hover:text-red-500">
                            123-456-7890
                        </a>

                    </div>

                </div>

            </div>

            <!-- CONTACT FORM -->
            <div class="bg-white
                flex flex-col
                p-5 sm:p-6 lg:p-8
                rounded-lg
                w-full lg:w-1/3
                min-w-0
                relative z-10
                shadow-md">

                <h2 class="text-gray-900
                    text-xl sm:text-2xl
                    mb-1 font-medium title-font">
                    Silingan
                </h2>

                <p class="leading-relaxed mb-5 text-gray-600">
                    Contact Us!
                </p>

                <!-- Name -->
                <div class="relative mb-4">

                    <label for="name" class="leading-7 text-sm text-gray-600">
                        Name
                    </label>

                    <input type="text" id="name" name="name" placeholder="Enter your name" autocomplete="name" class="w-full min-w-0
                        bg-white rounded
                        border border-gray-300
                        focus:border-red-500
                        focus:ring-2 focus:ring-red-200
                        text-base outline-none
                        text-gray-700
                        py-2 px-3
                        leading-7
                        transition-colors duration-200">

                </div>

                <!-- Email -->
                <div class="relative mb-4">

                    <label for="email" class="leading-7 text-sm text-gray-600">
                        Email
                    </label>

                    <input type="email" id="email" name="email" placeholder="Enter your email" autocomplete="email"
                        class="w-full min-w-0
                        bg-white rounded
                        border border-gray-300
                        focus:border-red-500
                        focus:ring-2 focus:ring-red-200
                        text-base outline-none
                        text-gray-700
                        py-2 px-3
                        leading-7
                        transition-colors duration-200">

                </div>

                <!-- Message -->
                <div class="relative mb-4">

                    <label for="message" class="leading-7 text-sm text-gray-600">
                        Message
                    </label>

                    <textarea id="message" name="message" placeholder="Write your message here..." class="w-full min-w-0
                        bg-white rounded
                        border border-gray-300
                        focus:border-red-500
                        focus:ring-2 focus:ring-red-200
                        h-32 sm:h-36
                        text-base outline-none
                        text-gray-700
                        py-2 px-3
                        resize-y
                        leading-6
                        transition-colors duration-200"></textarea>

                </div>

                <!-- Send Button -->
                <button type="button" class="w-full
                    text-white bg-red-500
                    border-0
                    py-3 px-6
                    focus:outline-none
                    hover:bg-red-600
                    active:bg-red-700
                    rounded-lg
                    text-base sm:text-lg
                    transition-colors duration-300
                    cursor-pointer">
                    Send
                </button>

                <p class="text-xs text-gray-500 mt-3 text-center">
                    Satisfy your cravings.
                </p>

            </div>

        </div>

    </section>
</template>
