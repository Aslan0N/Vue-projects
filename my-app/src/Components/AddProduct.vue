<template>
    <div id="add">
        <form @submit.prevent="handleAdd">
            <div class="form-group">
                <label for="id"></label>
                <input type="text" id="id" v-model="product.id">
                <label for="name"></label>
                <input type="text" id="name" v-model="product.productName">
                <label for="price"></label>
                <input type="text" id="price" v-model="product.unitPrice">
                <label for="stock"></label>
                <input type="text" id="stock" v-model="product.unitInStock">
            </div>
            <button type="submit" class="btn btn-sm btn-success">Add</button>
        </form>
    </div>
</template>

<script>
export default {
    data() {
        return {
            product: {
                id: '',
                productName: "",
                unitPrice: '',
                unitInStock: ''
            }
        }
    },
    methods:{
        handleAdd(){
            this.$emit("add-prod", this.product)
        }
    }
}
</script>
<style lang="scss"></style>