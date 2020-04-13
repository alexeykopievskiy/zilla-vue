<template>
  <v-card class="swapzilla-card" width="380">
    <v-card class="swapzilla-card__item">
      <v-select
        class="swapzilla-select"
        background-color="var(--v-border-base)"
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
        background-color="var(--v-border-base)"
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
          background-color="var(--v-border-base)"
          outlined
          height="50"
          single-line
          label="Withdraw amount"
        ></v-text-field>
        <v-btn
          @click="maxAmount()"
          color="var(--v-alpha-base)"
          width="47"
          height="32"
          class="swapzilla-btn"
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
      color: var(--v-label-base);
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

    &.v-text-field--outlined fieldset {
      border: 1px solid rgb(240, 240, 240);
    }

    &.v-text-field--outlined.v-input--is-focused fieldset,
    .v-text-field--outlined.v-input--has-state fieldset {
      border: 1px solid var(--v-info-base);
    }

    &.v-text-field--outlined > .v-input__control > .v-input__slot {
      min-height: 50px;
    }

    &.v-text-field--outlined .v-label {
      top: 15px;
    }

    &__container {
      position: relative;

      .swapzilla-btn {
        position: absolute;
        right: 9px;
        top: 9px;
      }
    }
  }

  &-btn {
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
        color: var(--v-white-base);
        font-size: 12px;
        letter-spacing: 0;
        font-weight: bold;
        box-shadow: none;
        border-radius: 5px;
      }
    }
}
</style>