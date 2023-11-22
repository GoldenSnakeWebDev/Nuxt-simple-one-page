<!-- Please remove this file from your project -->
    <template>
        <div>
            <Header/>
            <div class="px-[264px] pt-[70px] pb-[400px] min-h-screen sm:items-center bg-[#F9F9F9] gap-6">
                <div class="flex gap-8 justify-between">
                        <order-card v-for="(data, index) in order_card_data" :key="index" :order_img_url="data.order_icon_url" :order_value="data.order_value" :more_vertical_icon_url="data.more_vertical_icon_url" :order_arrow_icon_url="data.order_arrow_icon_url"/>
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
                    order_card_data: this.order_card_data 
                };
            },
        }
    </script>

  