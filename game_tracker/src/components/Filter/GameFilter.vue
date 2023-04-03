<template>
  <div class="order-by">
    <p class="filter-title">Ordernar por:</p>
    <div class="dropdown" @click="makeDropdown()">
      <div class="select">
        <span class="selected">% de Desconto</span>
      </div>
      <ul class="options">
        <li v-for="(filter_name, index) in filters" v-bind:key="index"> {{ filter_name }}</li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
    name: "GameFilter",
    data() {
        return {
            filters: ['% de Desconto', 'Maior preço', 'Menor preço', 'Título']
        }
    },
    methods: {
      makeDropdown() {
        const select = this.$el.querySelector(".select");
        const optionList = this.$el.querySelector(".options");
        const optionSelected = this.$el.querySelector("ul");
        
        select.addEventListener("click", function() {
          select.classList.add('active') 
          optionList.classList.add('open-options');
        });

        optionSelected.addEventListener("click", function() {
          select.classList.remove('active') 
          optionList.classList.remove('open-options');
        });
      }
    }
}
</script>

<style lang="scss">
@import "@/assets/scss/components/_filter.scss";
</style>