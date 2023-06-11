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
.Result {
    min-height: 100vh;
    padding: 20px;
    text-align: center;
    background-image: linear-gradient(125deg, rgb(31, 167, 167), #23b08d, #adadad, pink);
    background-size: 400%;
    animation: bgmove 20s infinite;
    background-position: 100%;
}

@keyframes bgmove {
    0% {
        background-position: 0% 50%;
    }

    50% {
        background-position: 100% 50%;
    }

    100% {
        background-position: 0% 50%;
    }
}
</style>