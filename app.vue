<template>
  <div class="container mt-3">
    <ul class="nav nav-pills" role="tablist">
      <li class="nav-item" v-for="state in states">
        <a :class="`nav-link ${state == selectedState ? 'active' : ''}`" data-toggle="pill" href="#order"
          @click="setSelectedState(state as states)">{{ state }}</a>
      </li>
    </ul>

   <div class="mt-3">
    <div v-if="!displayData.length">
      <h3 class="text-center">No data to display</h3>
    </div>
    <div class="d-flex flex-column">
      <Payments v-if="selectedState == 'Payments'"  v-for="data in displayData" :data="data" />
    </div>
   </div>
  </div>
</template>
<script setup lang="ts">
type states = "Orders" | "Recieve" | "Payments"
const states = ["Orders", "Recieve", "Payments"]
const selectedState = ref<states>("Orders");
const displayData = computed(() => data[selectedState.value])

const data = reactive({
  Orders: [

  ],
  Recieve: [
    {
      POId: 'PO-12-PO',
      product: 'nov-pro1',
      qty: 1,
      recieveQty: 1,
      recievedQty: 1,
      notRecievedQty: 0
    }
  ],
  Payments: [
    {
      paymentId: "sdfsdfsdf",
      paidBy: 'vvvs',
      raisedBy: 'sah',
      POId: 'PO-12-PO',
      recieptId: "dfdfs-dfdf",
      paymentDescription: 'Description',
      paymentDate: '2023-11-20',
      paymentAmount: '100',
    },
    {
      paymentId: "sdfsdfsdf",
      paidBy: 'vvvs',
      raisedBy: 'sah',
      POId: 'PO-12-PO',
      recieptId: "dfdfs-dfdf",
      paymentDescription: 'Description',
      paymentDate: '2023-11-20',
      paymentAmount: '100',
    }
  ]
})

const setSelectedState = (state: states) => selectedState.value = state
</script>
