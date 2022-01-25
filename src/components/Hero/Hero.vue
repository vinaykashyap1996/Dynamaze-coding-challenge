<template>
    <div>
        <img
            class="image"
            :src="imageSource"
        >
    </div>
</template>

<script>
import "./Hero.css";

export default {
    name: "Hero",
    props: {
        imageSource: {
            type: String,
            required: true,
        },
    },
};
</script>
