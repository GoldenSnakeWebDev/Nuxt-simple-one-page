    <!-- Please remove this file from your project -->
    <template>
        <div class="flex w-[330px] py-6 pl-6 pr-4 flex-column jsutify-center items-start gap-12 rounded-s-xl">
            <div class="flex justify-between items-start self-stretch">
                <div class="flex items-start gap-4">
                    <div class="flex p-2 justify-center items-center gap-[10px] rounded-full bg-[#007FF] opacity-25">
                        <div class="flex p-2 justify-center items-center gap-[10px] rounded-full bg-[#007FF]">
                            <img src={{total_order_url}} class="w-6 h-6 shrink-0"/>
                        </div>
                    </div>

                    <div class="flex items-start flex-column gap-3">
                        <p class="">

                        </p>
                        
                    </div>
                </div>
                <div class="">

                </div>
            </div>
            <p class="flex flex-column justify-center text-6 text-white font-medum">This is the home/landing for the dashboard client</p>
        </div>
    </template>
    
    <script>
    export default {
        name: 'OrderCard'
    }
    </script>
    