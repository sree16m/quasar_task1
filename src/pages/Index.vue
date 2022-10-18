<template>
  <!--q-page class="flex flex-center q-page" -->
  <q-page class="q-pt-lg q-pl-xl q-pr-xl">
    <div class="row justify-between items-center">
      <div class="col-12 gt-md">Available balance</div>
      <div class="col-6 lt-md">Available balance</div>
      <div class="col-6 lt-md text-right">
        <img src="~assets/Logo1.svg">
      </div>
      <h4>3,000</h4>
      <q-btn color="primary" icon="img:icons/box.svg" label="New card" class="gt-md" no-caps @click="addNewCard" />
      <q-btn :flat="true" color="primary" icon="img:icons/box.svg" label="New card" class="lt-md" no-caps @click="addNewCard" />
    </div>
    <q-tabs v-model="tab" dense class="text-grey" active-color="primary" indicator-color="primary" align="justify"
      narrow-indicator>
      <q-tab name="mails" label="My debit cards"  no-caps />
      <q-tab name="alarms" label="All company cards"  no-caps />
    </q-tabs>
    <q-card class="q-mt-sm">
      <q-tab-panels v-model="tab" animated>
        <q-tab-panel name="mails">
          <div class="row gt-md">
            <div class="col">
              <q-card :bordered="true" v-for="card in cards" :key="card.number">
                <q-card-section>
                  <div>{{card.holder}}</div>
                  <div>{{card.number_m}}</div>
                  <div>{{card.expiry}}</div>
                  <div>{{card.cvv_m}}</div>
                </q-card-section>
              </q-card>
              <q-space />
              <div class="toggles row justify-between text-center">
                <q-item tag="label" class="col-auto">
                  <q-item-section>
                    <q-checkbox v-model="freeze" checked-icon="img:icons/Freeze1.svg" size="64px"
                      unchecked-icon="img:icons/Freeze2.svg" />
                    <q-item-label>Freeze card</q-item-label>
                  </q-item-section>
                </q-item>
                <q-item tag="label" class="col-auto">
                  <q-item-section>
                    <q-checkbox size="64px" v-model="limit" checked-icon="img:icons/Spend1.svg"
                      unchecked-icon="img:icons/Spend2.svg" />
                    <q-item-label>Set spend limit</q-item-label>
                  </q-item-section>
                </q-item>
                <q-item tag="label" class="col-auto">
                  <q-item-section>
                    <q-checkbox size="64px" v-model="gpay" checked-icon="img:icons/Gpay1.svg" unchecked-icon="img:icons/Gpay1.svg" />
                    <q-item-label>Add to Gpay</q-item-label>
                  </q-item-section>
                </q-item>
                <q-item tag="label" class="col-auto">
                  <q-item-section>
                    <q-checkbox size="64px" v-model="replace" checked-icon="img:icons/Replace.svg"
                      unchecked-icon="img:icons/Replace.svg" />
                    <q-item-label>Replace card</q-item-label>
                  </q-item-section>
                </q-item>
                <q-item tag="label" class="col-auto">
                  <q-item-section>
                    <q-checkbox size="64px" v-model="cancel" checked-icon="img:icons/Cancel.svg"
                      unchecked-icon="img:icons/Cancel.svg" />
                    <q-item-label>Cancel card</q-item-label>
                  </q-item-section>
                </q-item>
              </div>
            </div>
            <div class="col">
              <q-expansion-item expand-separator icon="img:icons/Group11889.svg" label="Card details" no-wrap>
                <q-card>
                  <q-card-section>
                    Lorem ipsum dolor sit amet
                  </q-card-section>
                </q-card>
              </q-expansion-item>
              <q-expansion-item expand-separator icon="img:icons/Group11889-1.svg" label="Recent transactions" no-wrap>
                <q-card>
                  <q-card-section>
                    Lorem ipsum dolor sit amet
                  </q-card-section>
                </q-card>
              </q-expansion-item>
            </div>
          </div>
          <div class="lt-md">

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
      tab: 'mails',
      newCard:'',
      cards: [{
        number: '1111 1111 1111 1111',
        number_m: '**** **** **** 1111',
        holder: 'Mark Henry',
        expiry:'12/25',
        cvv:'007',
        cvv_m: '***',
        frozen: false
      }]
    }
  },
  methods: {
    addNewCard(){
      let newCard = {
        number: this.number,
        date: Date.now()
      };
      this.cards.unshift(newCard);
      //this.newCardContent = '';
    },
    deleteCard(card){
      let cardToDelete = card.number
      let index = this.cards.findIndex(card => card.number === cardToDelete);
      this.cards.splice(index, 1);
    }
  }
}
</script>
<style lang="sass">
.toggles .q-item__label
  font-size: 13px
  width: 70px

@media only screen and (max-width: 600px)
  body
    background-color: #0C365A
    color: #fff
  .q-page
    margin:10px
    padding:0
</style>