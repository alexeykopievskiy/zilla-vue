<template>
  <v-card class="swapzilla-card" width="380">
    <v-card class="swapzilla-card__item">
      <v-select
        class="swapzilla-select"
        background-color="#F0F0F0"
        :items="exchanges"
        filled
        height="50"
        full-width
        dense
        label="Choose exchange"
      ></v-select>
    </v-card>
    <v-card class="swapzilla-card__item">
      <v-select
        class="swapzilla-select"
        background-color="#F0F0F0"
        :items="currencies"
        filled
        height="50"
        full-width
        dense
        label="Choose currency"
      ></v-select>
    </v-card>
    <v-card class="swapzilla-card__item">
      <v-card class="swapzilla-input__container">
        <v-text-field
          class="swapzilla-input"
          background-color="#F0F0F0"
          solo
          label="Withdraw amount"
        ></v-text-field>
        <v-btn
          @click="maxAmount()"
          color="#C4C4C4"
          width="47"
          height="32"
          class="swapzilla-input__btn"
          tile
        >Max</v-btn>
      </v-card>
    </v-card>
    <v-btn
      @click="widthdraw()"
      class="swapzilla-card__btn"
      tile
      color="primary"
      height="50"
      block
      dark
    >Withdraw</v-btn>
  </v-card>
</template>

<script>
export default {
  data: () => {
    return {
      exchanges: ["Kraken", "Binance", "Upbit", "Kucoin", "OKEX"],
      currencies: ["BTC", "ETH", "BNB", "OKB", "USDT"]
    };
  },
  methods: {
    maxAmount: () => {
      console.log("max");
    },
    widthdraw: () => {
      console.log("withdraw");
    }
  }
};
</script>

<style lang="scss">
.swapzilla {
  &-input {
    .v-input__control {
      height: 50px;
    }

    &.v-text-field.v-text-field--solo:not(.v-text-field--solo-flat)
      > .v-input__control
      > .v-input__slot {
      box-shadow: none;
    }

    &.v-input .v-label {
      height: 19px;
      line-height: 19px;
      font-size: 14px;
      color: #9aa2a8;
    }

    &.v-text-field.v-text-field--enclosed:not(.v-text-field--rounded)
      > .v-input__control
      > .v-input__slot {
      padding: 0 9px 0 18px;
    }

    &.theme--light.v-input input {
      color: #3c484c;
      font-size: 14px;
    }

    &__container {
      position: relative;
    }

    &__btn {
      position: absolute;
      right: 9px;
      top: 9px;

      &.v-btn:not(.v-btn--round).v-size--default {
        min-width: 47px;
        padding: 0;
      }

      &.v-btn {
        text-transform: initial;
        width: 47px;
        padding: 0;
        min-width: 47px;
        height: 32px;
        color: #fff;
        font-size: 12px;
        letter-spacing: 0;
        font-weight: bold;
        box-shadow: none;
        border-radius: 5px;
      }
    }
  }
}
</style>