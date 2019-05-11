<template>
    <div class='row laptops-container p-5'>
        <div class='col-md-4' v-for='laptop in laptops' :key='laptop.id'>
            <Laptop :laptop='laptop' />
        </div>
    </div>
</template>

<script>
import Laptop from './Laptop.vue';

export default {
    name: 'laptops',
    components: {
        Laptop
    },
    props: {
        laptops: Array
    }
}
</script>

<style>
.laptops-container {
    height: 82.5%;
}
</style>
