<template>
    <div id="prices">
        <p class="displayText">
            Nur noch {{ ticketsLeft }} Tickets vorhanden.
        </p>
        <div class="counterContainer">
            <div
                class="decreaseIncreaseButtonContainer leftButton"
                @click="increaseCounter"
            >
                <div class="decreaseIncreaseButton">
                    <svg
                        class="increaseDescreaseSvg"
                        width="14"
                        height="14"
                        viewBox="0 0 14 14"
                        fill="none"
                        xmlns="http://www.w3.org/2000/svg"
                    >
                        <line
                            y1="7"
                            x2="14"
                            y2="7"
                            stroke="black"
                            stroke-width="2"
                        />
                        <line
                            x1="7"
                            y1="14"
                            x2="7"
                            stroke="black"
                            stroke-width="2"
                        />
                    </svg>
                </div>
            </div>
            <div class="numberOfTickets">
                {{ counter }} {{ counter > 1 ? "Tickets" : "Ticket" }}
            </div>
            <div
                class="decreaseIncreaseButtonContainer rightButton"
                @click="decreaseCounter"
            >
                <div class="decreaseIncreaseButton">
                    <svg
                        class="increaseDescreaseSvg"
                        width="14"
                        height="2"
                        viewBox="0 0 14 2"
                        fill="none"
                        xmlns="http://www.w3.org/2000/svg"
                    >
                        <line
                            y1="1"
                            x2="14"
                            y2="1"
                            stroke="black"
                            stroke-width="2"
                        />
                    </svg>
                </div>
            </div>
        </div>
        <div class="totalPrice">
            {{ priceTotal }} euros
        </div>
        <div class="positionButton">
            <div class="submitButtonContainer">
                <div
                    class="submitButton"
                    @click="submitBooking"
                >
                    <div class="buttonText">
                        Jetzt buchen
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import "./Price.css";
import moment from "moment";

export default {
    name: "Price",
    props: {
        ticketAmount: {
            type: Number,
            default: 0,
        },
        ticketPrice: {
            type: Number,
            default: 0,
        },
        ticketTime: {
            type: String,
            required: true,
        },
    },
    data: function () {
        return {
            totalAmount: 0,
            counter: 1,
        };
    },
    computed: {
        ticketsLeft: function () {
            return this.ticketAmount - this.counter;
        },
        priceTotal: function () {
            return this.counter * this.ticketPrice;
        },
    },
    methods: {
        displayAmount: function (amount, counter) {
            if (amount > 0 && counter > 0) {
                this.totalAmount = this.amount * this.counter;

                return this.totalAmount;
            } else {
                return 0;
            }
        },
        increaseCounter: function () {
            if (this.ticketsLeft > 0) this.counter = this.counter + 1;
            else return;
        },
        decreaseCounter: function () {
            if (this.counter == 1) {
                return;
            } else {
                this.counter = this.counter - 1;
            }
        },
        submitBooking: function (event) {
            alert(
                `Booking TimeSlot at ${moment(this.ticketTime, "h:mm a").format(
                    "h:mm a",
                )}, ${this.counter} tickets at ${this.priceTotal} € succeeded`,
            );
        },
    },
};
</script>
