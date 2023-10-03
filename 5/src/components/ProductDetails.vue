<template>
    <div>
        <p>Название: {{ product.name }}, цена: {{ formattedPrice }}, доступен:{{ isProdAvailable }}</p>
        <button @click="changeAvailable">{{ isProdAvailable }}?</button>
    </div>
</template>

<script>
export default {
    name: 'ProductDetails',

    data() {
        return {
            product: {
                name:'IPhone',
                price: 1000,
                available: true,
            },
        };
    },

    computed: {
        formattedPrice() {
            return `$${this.product.price}`;
        },
        isProdAvailable() {
            if (this.product.available) {
                return 'available'
            } else {
                return 'Out of stock'
            }
        }
    },

    methods: {
        changeAvailable() {
            console.log(this.product.available);
            this.product.available = !this.product.available;
        },
    },
};
</script>

<style lang="scss" scoped>

</style>