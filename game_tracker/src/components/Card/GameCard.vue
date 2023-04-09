<template>
    <div>
        <div class="main heading-options">
            <div class="order-by">
                <p class="filter-title">Ordernar por:</p>
                <div class="dropdown" @click="makeDropdown()">
                    <div class="select">
                        <span class="selected">{{ selectedFilter }}</span>
                    </div>
                    <ul class="options">
                        <li v-for="(filter_name, index) in filters" v-bind:key="index" @click="updateFilter(filter_name)">
                            {{ filter_name }}
                        </li>
                    </ul>
                </div>
            </div>
        </div>
        <div class="main">
            <div class="grid-container">
                <div class="grid-item card" v-for="(item, index) in listItems" v-bind:key="index">
                    <div class="game-thumb">
                        <img :src="item.thumb" alt="game thumbnail">
                    </div>
                    <div class="game-info">
                        <div>
                            <div class="game-title">
                                {{item.title}}
                            </div>
                        </div>
                        <div class="bottom-content">
                            <div class="details">
                                <button class="details-btn">
                                    <span>Detalhes</span>
                                </button>
                            </div>
                            <div class="buy">
                                <div class="game-price">
                                    <div class="normal-price">
                                        {{item.normalPrice}}
                                    </div>
                                    <div class="sale-price">
                                        {{item.salePrice}}
                                    </div>
                                </div>
                                <span class="savings">
                                    {{savingsArray[index]}}
                                </span>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: "GameCard",
     data() {
      return {
        listItems: [],
        savingsArray: [],
        savings: null,
        filters: ['% de Desconto', 'Maior preço', 'Menor preço', 'Título'],
        selectedFilter: "% de Desconto",
      }
    },
    methods: {
        async getData() {
            const res = await fetch("https://www.cheapshark.com/api/1.0/deals?pageNumber=0&pageSize=12&storeID=1&onSale=1&AAA=1");
            const finalRes = await res.json();
            this.listItems = finalRes;

            finalRes.forEach(obj => {
                const savingsValue = obj['savings'];
                const savingsInt = parseInt(savingsValue);
                this.savingsArray.push(savingsInt);
                this.texto = savingsInt;
            });
        },
        makeDropdown() {
            const select = this.$el.querySelector(".select");
            const optionList = this.$el.querySelector(".options");

            select.addEventListener("click", function() {
            select.classList.add('active') 
            optionList.classList.add('open-options');
            });

            optionList.addEventListener("click", function(e) {
                if (e.target && e.target.nodeName === "LI") {
                    const option = e.target.textContent;

                    const optionOutput = document.querySelector(".selected");
                    optionOutput.textContent = `${option}`;

                    select.classList.remove('active') 
                    optionList.classList.remove('open-options');
                }
            });
        },
        updateFilter(filter) {
            this.selectedFilter = filter;
            if (filter === "Maior preço") {
                this.filteredList = this.listItems.sort(
                    (a, b) => b.salePrice - a.salePrice
                );
            } else if (filter === "Menor preço") {
                this.filteredList = this.listItems.sort(
                    (a, b) => a.salePrice - b.salePrice
                );
            } else if (filter === "Título") {
                this.filteredList = this.listItems.sort((a, b) =>
                    a.title.localeCompare(b.title)
                );
            } else {
                this.filteredList = this.listItems.sort(
                    (a, b) => b.savings - a.savings
                );
            }
        },
    },
    mounted() {
      this.getData(),
      this.savings = this.$refs.savings,
      this.filteredList = this.listItems;
    }
}
</script>

<style lang="scss">
@import "@/assets/scss/components/card.scss";
@import "@/assets/scss/components/_filter.scss";
</style>