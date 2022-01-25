
<template>
    <Header />
    <DisplayImage :image-source="imageUrl" />
    <Contents :time-slots="timeSlots" />
    
<!--
    <p class="totalcost">
        {{ displayAmount(amount,counter) }} euros
    </p>
    <button
        class="submitbutton BookingButton"
        @click="greet"
    >
        Jetzt Buchen
    </button> -->
</template>

<script>
import Header from "./components/Header/Header.vue";
import DisplayImage from "./components/Image/DisplayImage.vue";
import Contents from "./components/contents/contents.vue";

export default {
    name: 'App',
    components: {
        Header, 
        DisplayImage,
        Contents,
    },
    data: function() {
        return {
            imageUrl:"https://firebasestorage.googleapis.com/v0/b/dynamaze---pwa-1550221436823.appspot.com/o/public%2Fimg%2Fdeals%2Ffunfussball1.png?alt=media&token=448599c6-ffb7-43f4-afc9-dfb82ce426f0",
            selectedAmount: 1,
            date:null,
            amount:0,
            activeId:0,
            isAddClass: false,
            sum:0,
            selected:undefined,
            timeSlots: [
                {
                    id: "1",
                    ticketAmount: 10,
                    begin: "10:00",
                    price: {
                        amount: 10,
                        currency: "EUR",
                    },
                },
                {
                    id: "2",
                    ticketAmount: 5,
                    begin: "11:00",
                    price: {
                        amount: 12,
                        currency: "EUR",
                    },
                },
            ], 

        };
    },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.text1{
position: relative;
font-family: Montserrat;
font-style: normal;
font-weight: normal;
font-size: 16px;
color: #222222;
}
body{
    margin:0
}
</style>
