<template>
 <div class="card mb-3">
      <div class="card-body">
        <div class="d-flex justify-content-between align-items-center">
          <div>
            <p class="mb-0 ">Payment # {{ data.paymentId }}</p>
            <p class="mb-0">Raised By: {{ data.raisedBy }}</p>
          </div>
          <div class="text-end">
            <p class="mb-0">Paid By: {{ data.paidBy }}</p>
            <p class="mb-0">Payments: {{ data.POId }}</p>
          </div>
        </div>
        <div class="table-responsive mt-3">
          <table class="table mb-0">
            <thead class="bg-gray-800">
              <tr>
                <th>Receipt #</th>
                <th>Payment Description</th>
                <th>Payment Date</th>
                <th>Payment Amount</th>
              </tr>
            </thead>
            <tbody>
              <tr>
                <td class="">{{ data.paymentId }}</td>
                <td>{{data.paymentDescription}}</td>
                <td class="">{{ data.paymentDate }}</td>
                <td>{{ data.paymentAmount }}</td>
              </tr>
            </tbody>
          </table>
        </div>
      </div>
    </div>
</template>
<script setup lang="ts">
interface IPayments {
    paymentId: String,
    paidBy: String,
    raisedBy: String,
    POId: String,
    recieptId: String,
    paymentDescription: String,
    paymentDate: String,
    paymentAmount: String,
}

const props = defineProps({
  data: Object
})
</script>