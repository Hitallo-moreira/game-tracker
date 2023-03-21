<template>
    <div>
        <div>
            <div class="main grid-container">
                <div class="grid-item card" v-for="(item, index) in listItems" v-bind:key="index">
                    <div class="game-thumb">
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
                                    <div class="sale-price">
                                        {{item.salePrice}}
                                    </div>
                                    <div class="normal-price">
                                        {{item.normalPrice}}
                                    </div>
                                </div>
                                <button class="addtocart">
                                    <span>{{item.savings}}</span>
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
        this.listItems = finalRes;
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