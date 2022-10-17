<template>
  <!--q-page class="flex flex-center q-page" -->
  <q-page class="q-pt-lg q-pl-xl q-pr-xl">
    <div class="row justify-between">
        <div class="col-12">Available Balance</div>
        <div>First column</div>
        <div>Second column</div>
      </div>
    <!--q-toolbar >
      <q-toolbar-title class="text-black">Available Balance </q-toolbar-title>

      <q-btn flat round dense icon="whatshot" />
    </q-toolbar-->
    <q-tabs
          v-model="tab"
          dense
          class="text-grey"
          active-color="primary"
          indicator-color="primary"
          align="justify"
          narrow-indicator
    >
      <q-tab name="mails" label="My debit cards" />
      <q-tab name="alarms" label="All company cards" />
    </q-tabs>
    <q-card class="q-mt-sm">
      <q-tab-panels v-model="tab" animated>
        <q-tab-panel name="mails">
          <div class="text-h6">Mails</div>
          Lorem ipsum dolor sit amet consectetur adipisicing elit.
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
export default {
  name: 'PageIndex',
  data () {
    return {
      tab: 'mails'
    }
  }
}
</script>