<template>
  <div>
    <img class="image" :src="imageSource" />
  </div>
</template>

<script>
import "./DisplayImage.css";

export default {
  name: "DisplayImage",
  props: {
    imageSource: {
      type: String,
      required: true,
    },
  },
};
</script>
