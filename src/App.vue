<template>
  <v-app>
    <v-content>
      <v-row justify="center">
        <v-dialog v-model="dialog" persistent max-width="790">
          <template v-slot:activator="{ on }">
            <v-btn justify="center" color="primary" dark v-on="on">Open Dialog</v-btn>
          </template>
          <v-card>
            <v-tabs slider-size="4" height="93" v-model="tab" class="swapzilla-tabs" light>
              <v-tabs-slider></v-tabs-slider>

              <v-tab v-for="(tab, index) in tabs" :key="tab" :href="`#tab-${index}`">{{tab}}</v-tab>
              <v-btn class="swapzilla-tabs__close" @click="dialog=false" icon right color="#9AA2A8">
                <v-icon size="32">mdi-close</v-icon>
              </v-btn>
              <v-tab-item class="swapzilla-tabs__item" :value="'tab-0'">
                <Deposit />
              </v-tab-item>
              <v-tab-item class="swapzilla-tabs__item" :value="'tab-1'">
                <Withdraw />
              </v-tab-item>
              <v-tab-item class="swapzilla-tabs__item" :value="'tab-2'">
                <Rebalance />
              </v-tab-item>
            </v-tabs>
          </v-card>
        </v-dialog>
      </v-row>
    </v-content>
  </v-app>
</template>

<script>
import Deposit from "@/components/Deposit";
import Withdraw from "@/components/Withdraw";
import Rebalance from "@/components/Rebalance";

export default {
  name: "App",
  components: {
    Deposit,
    Withdraw,
    Rebalance
  },
  data() {
    return {
      tab: null,
      tabs: ["Deposit", "Withdraw", "Rebalance"],
      dialog: false
    };
  }
};
</script>

<style lang="scss">
@import url("https://fonts.googleapis.com/css2?family=Open+Sans:wght@400;600;700&display=swap");

.swapzilla {
  &-tabs {
    font-family: "Open Sans", sans-serif;
    position: relative;

    &__close {
      position: absolute;
      right: 26px;
      top: 26px;
    }

    &.theme--light.v-tabs > .v-tabs-bar .v-tab:not(.v-tab--active) {
      color: var(--v-label-base);
    }

    .v-tabs-slider {
      background-color: var(--v-dark-base);
    }

    .v-tabs-bar {
      &__content {
        padding: 33px 40px 14px;
        height: 80px;
      }
    }

    .v-tab {
      text-transform: initial;
      font-size: 20px;
      line-height: 27px;
      letter-spacing: 0;
      color: var(--v-label-base);
      padding: 0;
      font-weight: 400;
      min-width: auto;
      margin-right: 40px;
      height: 30px;

      &.v-tab {
        color: var(--v-dark-base);
      }

      &--active {
        color: var(--v-dark-base);
      }

      &:last-child {
        margin-right: 0;
      }
    }

    &__item {
      .v-card {
        box-shadow: none;
      }
    }
  }
}
</style>
