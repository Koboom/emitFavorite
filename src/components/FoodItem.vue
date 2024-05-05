<script>
    export default {
        props: {
            foodName: {
                type: String,
                required: true,
                default: "Food Name"
            },
            foodDesc: {
                type: String,
                required: true,
                default: "Food Desc"
            },
            isFavorite: {
                type: Boolean,
                required: false
            }
        },
        methods: {
            toggleFavorite() {
                this.$emit("toggle-favorite", this.foodName)
            }
        }
    }
</script>

<template>
    <div class="w3-container">
        <h2>
            {{ foodName }}
            <img src="../components/icons/img_quality.svg" alt="" v-show="isFavorite" style="height: 1.5em; float: right;">
        </h2>
        <p>{{ foodDesc }}</p>

        <button @click="toggleFavorite" class="w3-button w3-black w3-hover-red w3-round-large">Favorite</button>
    </div>
</template>

<style></style>