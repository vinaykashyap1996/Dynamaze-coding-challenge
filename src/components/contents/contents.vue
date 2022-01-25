<template>
  <div class="Booking">
    <div class="timeSlots">
      <Button
        v-for="timeSlot in timeSlots"
        :key="timeSlot.id"
        :begin="timeSlot.begin"
        :ticket-price="timeSlot.price.amount"
        :selected="timeSlot.id == selectedSlot.id"
        @click="selectedSlot = timeSlot"
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
import "./contents.css";

export default {
  name: "Content",
  components: {
    Price,
    Button,
  },
  props: {
    timeSlots: {
      type: Object,
      default: function () {
        return {};
      },
    },
  },
  data: function () {
    return { selectedSlot: this.timeSlots[0] };
  },
};
</script>
