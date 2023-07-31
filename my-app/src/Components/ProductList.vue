<template>
    <div id="list">
        <table class="table">
            <thead>
                <tr>
                    <th scope="col">#</th>
                    <th scope="col">Product Name</th>
                    <th scope="col">Price</th>
                    <th scope="col">Stock</th>
                    <th scope="col"></th>
                </tr>
            </thead>
            <tbody>
                <tr v-for="product in products" :key="product.id">
                    <th scope="row" v-if="updateId === product.id">
                        <input type="text" v-model="product.id">
                    </th>
                    <th v-else scope="row">{{ product.id }}</th>

                    <td v-if="updateId === product.id">
                        <input type="text" v-model="product.productName">
                    </td>
                    <td v-else>{{ product.productName }}</td>

                    <td v-if="updateId === product.id">
                        <input type="text" v-model="product.unitPrice">
                    </td>
                    <td v-else>{{ product.unitPrice }}</td>
                    <td v-if="updateId === product.id">
                        <input type="text" v-model="product.unitInStock">
                    </td>
                    <td v-else>{{ product.unitInStock }}</td>
                    <!-- Buttons -->
                    <td v-if="updateId === product.id">
                        <button class="btn btn-warning btn-sm" >Save</button>
                        <button class="btn btn-danger btn-sm ms-1" @click="updateId = null">Cancel</button>
                    </td>
                    <td v-else>
                        <button class="btn btn-warning btn-sm" @click="updateId = product.id">Edit</button>
                        <button class="btn btn-danger btn-sm ms-1" @click="handleDelete(product)">Remove</button>
                    </td>
                </tr>

            </tbody>
        </table>
    </div>
</template>

<script>
export default {
    name: "List-product",
    props: {
        products: Array
    },
    data() {
        return {
            updateId: null
        }
    },
    methods: {
        handleDelete(product) {
            this.$emit("delete-prod", product)
        }
    }
}
</script>

<style lang="scss"></style>