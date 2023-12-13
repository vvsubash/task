<template>
    <div class="container">
        <table class="table ">
            <thead>
                <tr class="bg-secondary">
                    <th class="bg-secondary fw-normal">Product</th>
                    <th class="bg-secondary fw-normal">PO Qty.</th>
                    <th class="bg-secondary fw-normal">Receive Qty.</th>
                    <th class="bg-secondary fw-normal">Received Qty. (Total)</th>
                    <th class="bg-secondary fw-normal">Not Received Qty. (Total)</th>
                </tr>
            </thead>
            <tbody>
                <tr v-for="recieve in data" :key="recieve.sku">
                    <td>
          <div class="text-primary">{{ recieve.product }}</div>
          <div class="text-muted">sku: {{ recieve.sku }} </div>
        </td>
                    <td>{{ recieve.qty }}</td>
                    <td>{{ recieve.recieveQty }}</td>
                    <td>{{ recieve.recievedQty }}</td>
                    <td>{{ recieve.notRecievedQty }}</td>
                </tr>
            </tbody>
        </table>
    </div>
</template>
<script setup lang="ts">
interface IData {
    POId: String,
    product: String,
    qty: number,
    recieveQty: number,
    recievedQty: number,
    notRecievedQty: number,
    sku: String
}
const props = defineProps({
    data: Array
})
</script>