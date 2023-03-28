<template>
    <div class="load-content">
        <button class="load-btn">
            <span>{{ more_content }}</span>
        </button>
    </div>
</template>

<script>

export default {
    name: "LoadButton",
    data() {
        return {
            more_content: "Carregar mais"
        }
    }
}
</script>

<style lang="scss" scoped>
@import "@/assets/scss/components/_load-button.scss";
</style>
