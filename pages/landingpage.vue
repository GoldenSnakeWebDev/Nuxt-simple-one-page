<!-- Please remove this file from your project -->
    <template>
        <div>
            <Header/>
            <div class="min-w-max min-h-screen lg:px-[5px] xl:px-[calc(100%/7)] xl:flex-wrap pt-[70px] pb-[400px] bg-[#F9F9F9] gap-6">
                <div class="flex gap-8 justify-between">
                        <order-card v-for="(data, index) in order_card_data" :key="index" :order_img_url="data.order_icon_url" :order_value="data.order_value" :more_vertical_icon_url="data.more_vertical_icon_url" :order_arrow_icon_url="data.order_arrow_icon_url" :title="data.title" :icon_color1="data.icon_color1" :icon_color2="data.icon_color2"/>
                </div>

                <div class="bg-white flex gap-1 items-center mt-9 p-2 rounded-lg shadow-custom">
                    <ul class="flex">
                        <li class="flex px-6 py-3 justify-center items-center">
                            <img :src="home_icon_url" alt="home"/>
                        </li>
                        <li class="flex px-6 py-3 justify-center items-center text-black font-Poppins text-sm font-medium">
                            <p>Orders</p>
                        </li>

                        <li class="flex px-6 py-3 justify-center items-center text-black font-Poppins text-sm font-medium">
                            <p>Favorites</p>
                        </li>

                        <li class="flex px-6 py-3 justify-center items-center text-black font-Poppins text-sm font-medium">
                            <p>Messages</p> <p class="ml-4 text-grey" v-if="messages>0">{{ messages }}</p>
                        </li>

                        <li class="flex px-6 py-3 justify-center items-center text-black font-Poppins text-sm font-medium">
                            <p>Organization</p>
                        </li>

                        <li class="flex px-6 py-3 justify-center items-center text-black font-Poppins text-sm font-medium">
                            <p>Users</p> <div class=" bg-[#F9F9F9] ml-4"><p class="text-xs text-grey" v-if="users>0">{{ users }}</p></div>
                        </li>

                        <li class="flex px-6 py-3 justify-center items-center text-black font-Poppins text-sm font-medium">
                            <p>Shipping</p>
                        </li>

                        <li class="flex px-6 py-3 justify-center items-center text-black font-Poppins text-sm font-medium">
                            <p>Billing</p>
                        </li>

                        <li class="flex px-6 py-3 justify-center items-center text-black font-Poppins text-sm font-medium">
                            <p>Transaction History</p>
                        </li>

                        <li class="flex px-6 py-3 justify-center items-center text-black font-Poppins text-sm font-medium">
                            <p>Docs</p> <p class="ml-4" v-if="docs>0">{{ docs }}</p>
                        </li>

                        <li class="flex px-6 py-3 justify-center items-center text-black font-Poppins text-sm font-medium">
                            <p>Settings</p>
                        </li>
                    </ul>
                </div>
            </div>

        </div>
    </template>       
    
    <script>
        import Header from '../components/Header.vue'
        import OrderCard from '../components/OrderCard.vue'
        
        export default {
            name: 'landingpage',
            components: { OrderCard, Header },
            async fetch() {
                this.order_card_data = await this.$axios.$get('/mock data/orderData.json');
            },
            data() {
                return {
                    order_card_data: this.order_card_data,
                    home_icon_url: "/img/home 03.svg",
                    messages:130,
                    users: 40,
                    docs: 8
                };
            },
        }
    </script>

  