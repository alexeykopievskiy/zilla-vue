<template>
  <v-card class="swapzilla-card" width="380">
    <v-card class="swapzilla-card__item">
      <v-card class="swapzilla-select__container">
        <v-card-text class="swapzilla-select__label">From</v-card-text>
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
    </v-card>
    <v-card class="swapzilla-card__item">
      <v-card class="swapzilla-select__container">
        <v-card-text class="swapzilla-select__label">To</v-card-text>
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
      <v-text-field
        class="swapzilla-input"
        background-color="var(--v-border-base)"
        outlined
        height="50"
        single-line
        label="Withdraw amount"
      ></v-text-field>
    </v-card>
    <v-card class="swapzilla-card__item swapzilla-card__item--content">
      <v-card class="swapzilla-card__item swapzilla-card__item--small">
        <v-chip label color="#eaf0f4" class="swapzilla-badge">Balance:<span>0.0435628</span></v-chip>
      </v-card>
      <v-card class="swapzilla-card__item swapzilla-card__item--small">
        <v-btn
          v-for="item in btns"
          :key="item"
          color="var(--v-alpha-base)"
          width="47"
          height="32"
          class="swapzilla-btn"
          tile
        >{{item}}</v-btn>
      </v-card>
    </v-card>
  </v-card>
</template>

<script>
export default {
  data: () => {
    return {
      exchanges: ["Kraken", "Binance", "Upbit", "Kucoin", "OKEX"],
      currencies: ["BTC", "ETH", "BNB", "OKB", "USDT"],
      btns: ["10%", "25%", "50%", "100%", "Split"]
    };
  }
};
</script>

<style lang="scss">
.swapzilla-select {
  &__label {
    &.v-card__text {
      font-size: 12px;
      color: #3c484c;
      padding: 0 0 10px 18px;
    }
  }
}

.swapzilla-card {
  &__item {
    &--content.v-card {
      box-shadow: 0px 6px 6px rgba(60, 72, 76, 0.06) !important;
      border: 1px solid var(--v-border-base);
      padding: 20px;
      margin-top: -19px;

      .swapzilla-btn {
        margin-right: 10px;
      }
    }

    &--small {
      margin-bottom: 10px;
    }
  }
}

.swapzilla-badge {
  &.theme--light.v-chip {
    color: var(--v-primary-base);
  }

  &.v-chip.v-size--default {
    font-size: 12px;
  }

  .v-chip__content {
    span {
      font-weight: bold;
      display: inline-block;
      margin-left: 5px;
    }
  }
}
</style>