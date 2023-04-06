<template>
    <div>
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
                                <button class="savings">
                                    <span id="saving-label">
                                        {{ item.savings }}
                                    </span>
                                </button>
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
        listItems: []
      }
    },
    methods: {
        async getData() {
            const res = await fetch("https://www.cheapshark.com/api/1.0/deals?pageNumber=0&pageSize=12&storeID=1&onSale=1&AAA=1");
            const finalRes = await res.json();
            const savingsArray = [];
            this.listItems = finalRes;


            finalRes.forEach(obj => {
                const savingsValue = obj['savings'];
                const savingsInt = parseInt(savingsValue);
                savingsArray.push(savingsInt);
            });
        }
    },
    mounted() {
      this.getData()
    }
}
</script>

<style lang="scss">
@import "@/assets/scss/components/card.scss";
</style>