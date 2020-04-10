<template>
  <v-app>
    <v-content>
      <v-row justify="center">
        <v-dialog persistent max-width="600">
          <template v-slot:activator="{ on }">
            <v-btn justify="center" color="primary" dark v-on="on">Open Dialog</v-btn>
          </template>
          <v-card>
            <v-tabs
              v-model="tab"
              background-color="deep-purple accent-4"
              class="elevation-2"
              dark
              :centered="centered"
              :grow="grow"
              :vertical="vertical"
              :right="right"
              :prev-icon="prevIcon ? 'mdi-arrow-left-bold-box-outline' : undefined"
              :next-icon="nextIcon ? 'mdi-arrow-right-bold-box-outline' : undefined"
              :icons-and-text="icons"
            >
              <v-tabs-slider></v-tabs-slider>

              <v-tab v-for="(tab, index) in tabs" :key="tab" :href="`#tab-${index}`">
                {{tab}}
              </v-tab>

              <v-tab-item :value="'tab-0'">
                <Deposit />
              </v-tab-item>
              <v-tab-item :value="'tab-1'">
                <Withdraw />
              </v-tab-item>
              <v-tab-item :value="'tab-2'">
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
import Deposit from '@/components/Deposit'
import Withdraw from '@/components/Withdraw'
import Rebalance from '@/components/Rebalance'

export default {
  name: "App",
  components: {
    Deposit, Withdraw, Rebalance
  },
  data() {
    return {
      tab: null,
      text:
        "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.",
      icons: false,
      centered: false,
      grow: false,
      vertical: false,
      prevIcon: false,
      nextIcon: false,
      right: false,
      tabs: ['Deposit', 'Withdraw', 'Rebalance']
    };
  }
};
</script>
