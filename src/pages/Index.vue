<template>
  <!--q-page class="flex flex-center q-page" -->
  <q-page class="q-pt-lg q-pl-xl q-pr-xl">
    <div class="row justify-between">
      <div class="col-12">Available Balance</div>
      <div>First column</div>
      <div>Second column</div>
    </div>
    <q-tabs v-model="tab" dense class="text-grey" active-color="primary" indicator-color="primary" align="justify"
      narrow-indicator>
      <q-tab name="mails" label="My debit cards" />
      <q-tab name="alarms" label="All company cards" />
    </q-tabs>
    <q-card class="q-mt-sm">
      <q-tab-panels v-model="tab" animated>
        <q-tab-panel name="mails">
          <div class="row">
            <div class="col">
              <q-toolbar>
                <q-space />
                <q-btn flat round dense icon="assignment_ind" />
                <q-btn flat round dense icon="sim_card" class="q-mr-xs" />
                <q-btn flat round dense icon="gamepad" />
                <q-space />
              </q-toolbar>
              <q-space />
              <div class="row justify-between">
                <q-item tag="label" class="col-auto">
                  <q-item-section>
                    <q-checkbox v-model="freeze" checked-icon="img:icons/Logo1.svg"
                      unchecked-icon="img:icons/Card.svg" />
                    <q-item-label>Freeze card</q-item-label>
                  </q-item-section>
                </q-item>
                <q-item tag="label" class="col-auto">
                  <q-item-section>
                    <q-checkbox v-model="limit" checked-icon="img:icons/Logo1.svg"
                      unchecked-icon="img:icons/Card.svg" />
                    <q-item-label>Set spend limit</q-item-label>
                  </q-item-section>
                </q-item>
                <q-item tag="label" class="col-auto">
                  <q-item-section>
                    <q-checkbox v-model="gpay" checked-icon="img:icons/Logo1.svg" unchecked-icon="img:icons/Card.svg" />
                    <q-item-label>Add to Gpay</q-item-label>
                  </q-item-section>
                </q-item>
                <q-item tag="label" class="col-auto">
                  <q-item-section>
                    <q-checkbox v-model="replace" checked-icon="img:icons/Logo1.svg"
                      unchecked-icon="img:icons/Card.svg" />
                    <q-item-label>Replace card</q-item-label>
                  </q-item-section>
                </q-item>
                <q-item tag="label" class="col-auto">
                  <q-item-section>
                    <q-checkbox v-model="cancel" checked-icon="img:icons/Logo1.svg"
                      unchecked-icon="img:icons/Card.svg" />
                    <q-item-label>Cancel card</q-item-label>
                  </q-item-section>
                </q-item>
              </div>

              <q-space />
              </q-toolbar>
            </div>
            <div class="col">
              <q-expansion-item expand-separator icon="signal_wifi_off" label="Wifi settings">
                <q-card>
                  <q-card-section>
                    Lorem ipsum dolor sit amet
                  </q-card-section>
                </q-card>
              </q-expansion-item>
              <q-expansion-item expand-separator icon="signal_wifi_off" label="Wifi settings">
                <q-card>
                  <q-card-section>
                    Lorem ipsum dolor sit amet
                  </q-card-section>
                </q-card>
              </q-expansion-item>
            </div>
          </div>
        </q-tab-panel>
        <q-tab-panel name="alarms">
          <div class="text-h6">Alarms</div>
          Lorem ipsum dolor sit amet consectetur adipisicing elit.
        </q-tab-panel>
      </q-tab-panels>
    </q-card>
  </q-page>
</template>

<script>
import { ref } from 'vue'

export default {
  name: 'PageIndex',
  data() {
    return {
      freeze: ref(true),
      limit: ref(true),
      gpay: ref(true),
      replace: ref(true),
      cancel: ref(true),
      tab: 'mails'
    }
  }
}
</script>
<style lang="sass">
.q-item__label
  font-size: 13px
  width: 70px
</style>