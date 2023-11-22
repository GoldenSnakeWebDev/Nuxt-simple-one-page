<!-- Please remove this file from your project -->
    <template>
        <div>
            <Header/>
            <div class="px-[264px] pt-[70px] pb-[400px] min-h-screen sm:items-center bg-[#F9F9F9] gap-6">
                
                <order-card :total_order_img_url="total_order_img_url" :total_order_value="total_order_value" :more_vertical_icon_url="more_vertical_icon_url" :order_arrow_icon_url="order_arrow_icon_url"/>
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
                const orderResponse = await this.$axios.$get('/mock data/orderData.json');
                console.log("json data>>>>", orderResponse);
                this.total_order_value = orderResponse.total_order_value;
                this.total_order_img_url = orderResponse.total_order_img_url;
                this.more_vertical_icon_url = orderResponse.more_vertical_icon_url;
                

                console.log("total order value>>>", this.total_order_value);
            },
            data() {
                return {
                    total_order_img_url:"/img/total-order-image.svg",
                    more_vertical_icon_url:"/img/more-vertical.svg",
                    total_order_value:this.total_order_value,
                    order_arrow_icon_url: "/img/arrow-right.svg"
                };
            },
        }
    </script>

  