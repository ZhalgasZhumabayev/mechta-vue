<template>
    <ul class="wrap-shipping-cost">
        <li class="shipping-cost" v-for="d in delivery" v-bind:class="{ 'inactive': !d.available}" v-on:click="selected = d.type" :key="d.type">
            <span class="shipping-cost-type">{{ d.type }}</span>
            <span class="shipping-cost-price">${{ d.price }}</span>

            <img class="shipping-cost-img" :src="`/images/${d.type.toLowerCase()}.svg`" alt="">
            <div v-if="d.available" class="selected" v-bind:style='{"display": ( d.type == selected ? "block" : "none")}'>
                <img class="tick" src="/images/tick.svg" alt="tick">
            </div>
        </li>
    </ul>
</template>

<script>
    export default {
        name: "shippingcost",
        props: {
            delivery: Array,
        },
        data: function () {
          return {
              selected: undefined,
          }
        },
        methods: {

        }
    }
</script>

<style scoped>

</style>