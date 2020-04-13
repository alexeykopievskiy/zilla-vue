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
      <v-img
        class="swapzilla-card__img"
        :src="require('../assets/qr.svg')"
        contain
        width="119"
        height="112"
      />
    </v-card>
    <v-card class="swapzilla-card__item">
      <v-card-text class="swapzilla-card__text">FGBfvcnkfdnvkk74365832ybvcvdfvfvb</v-card-text>
    </v-card>
    <v-btn
      @click="copyAddress()"
      class="swapzilla-card__btn"
      tile
      color="primary"
      height="50"
      block
      dark
    >Copy</v-btn>
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
    copyAddress: () => {
      console.log("click");
    }
  }
};
</script>

<style lang="scss">
.swapzilla-select {

  &.v-text-field--filled.v-input--dense.v-text-field--single-line .v-label,
  .v-text-field--full-width.v-input--dense.v-text-field--single-line .v-label {
    top: 15px;
  }

  &.v-text-field.v-text-field--enclosed:not(.v-text-field--rounded)
    > .v-input__control
    > .v-input__slot {
    padding: 0 12px 0 18px;
  }

  &.v-text-field > .v-input__control > .v-input__slot {
    &:before,
    &:after {
      border: none;
    }
  }

  .v-input__append-inner {
    margin-top: 20px;
  }

  &.theme--light.v-select .v-select__selection--comma {
    font-size: 14px;
    color: var(--v-dark-base);
  }

  &.v-text-field--full-width.v-input--dense:not(.v-text-field--solo).v-text-field--single-line
    .v-input__append-inner {
    margin-top: 14px;
  }

  .v-icon,
  .v-icon.primary--text {
    color: var(--v-label-base) !important;
  }

  &.v-input .v-label {
    height: 19px;
    line-height: 19px;
    font-size: 14px;
    color: var(--v-label-base);
  }

  &.v-input--dense > .v-input__control > .v-input__slot {
    margin-bottom: 0;
  }

  .v-input__control {
    height: 50px;
  }
}

.swapzilla {
  &-card {
    &.v-card {
      box-shadow: none;
      padding: 41px 0 71px;
      margin: auto;
    }

    &__item {
      margin-bottom: 20px;

      &.v-card {
        *:last-child:not(.v-btn):not(.v-chip) {
          border-radius: 5px;
        }
      }

      &:last-child {
        margin-bottom: 0;
      }
    }

    &__img {
      margin: 37px auto 0;
    }

    &__text {
      text-align: center;

      &.v-card__text {
        padding: 7px 0 9px 0;
      }
    }

    &__btn {
      &.v-btn {
        border-radius: 5px;
        text-transform: initial;
        font-size: 14px;
        font-weight: 700;
      }
    }
  }
}
</style>