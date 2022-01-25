<template>
    <div class="Booking">
        <div class="timeSlots">
            <Button
                v-for="ts in timeSlots"
                :key="ts.id"
                :begin="ts.begin"
                :ticket-price="ts.price.amount"
                :selected="ts.id == selectedSlot.id"
                @click="selectedSlot = ts"
            />
        </div>
        <Price 
            :ticket-amount="selectedSlot.ticketAmount"
            :ticket-price="selectedSlot.price.amount"
            :ticket-time="selectedSlot.begin"
        />
    </div>
</template>

<script>
import Price from "../Prices/Price.vue";
import Button from "../Button/Button.vue";

export default {
    name:"Content",
    components:{
        Price,
        Button,
    },
    props: {
        timeSlots: {
            type: Object,
            default: function() { return {}; },
        },
    },
    data:function(){
        return{ selectedSlot: this.timeSlots[0]};
    },
};
</script>

<style scoped>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.Booking {
        display: flex;
        flex-direction: column;
        height: 100%;
        margin:20px;
    }
.timeSlots{
    display: flex;
    justify-content: space-between;
    margin: 1vw 5vw 1vw 5vw;
}
</style>