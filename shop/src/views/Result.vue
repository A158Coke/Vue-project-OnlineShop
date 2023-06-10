<template>
    <div class="Result">
        <ul v-for="Producto of Productos" :key="Producto.id">
            <img :src="Producto.img" alt="Product Image(not showing?)" class="product-image" />
            <li>{{ Producto.nombre }}</li>
            <li>{{ Producto.descrip }}</li>
            <li>{{ Producto.precio }} $</li>
        </ul>
    </div>
</template>
<script>
import axios from 'axios';
export default {
    name: "Result",
    data() {
        return {
            Producto: {},
            Productos: [],
        }
    },

    created() {
        const search = this.$route.params.search;
        axios.get(`http://localhost:3000/Search/${search}`)
            .then((response) => {
                console.log(response.data);
                this.Productos = response.data;
            })
            .catch((error) => {
                console.error(error);
            });
    }

}
</script>
<style scoped>

</style>