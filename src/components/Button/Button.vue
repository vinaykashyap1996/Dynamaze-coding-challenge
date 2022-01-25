<template>
    <div class="bookingOption">
        <div class="buttonContainer">
            <div :class="'button ' + selection">
                <div class="dataContainer">
                    <div
                        class="time"
                        :class="{whiteColor : selected}"
                    >
                        {{ begin }}
                    </div>
                    <div
                        class="dividerline"
                        :class="{whiteBorder : selected}"
                    />
                    <div
                        class="price"
                        :class="{whiteColor : selected}"
                    >
                        {{ toFixed(ticketPrice) }}
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import './Button.css';

export default {
    name:"Button",
    props:{
        begin:{
            type:String,
            required:true,
        },
        ticketPrice:{
            type:Number,
            default:0,
        },
        selected: {
            type: Boolean,
            default: false,
        },
       
    },
   
    computed: {
        selection: function() { return this.selected ? 'isActive' : 'inActive'; },
    },
    methods:{
        toFixed:function(amount){
            return amount.toLocaleString('de-DE', { style: 'currency', currency: 'EUR' });
        },
    },
};
</script>