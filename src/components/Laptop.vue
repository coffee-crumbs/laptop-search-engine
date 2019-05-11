<template>
    <div class='card shadow-lg laptop-container'>
        <div class='card-body laptop-info'>
            <div class='card-title text-center laptop-title'>
                <h5>{{ laptop.model }}</h5>
            </div>
            <p class="card-text">Price: {{ this.convertToUsdFormat(laptop.price) }}</p>
            <p class="card-text">
                <span>Rating:&nbsp;</span>
                <span v-for='star in laptop.rating' :key='"star: "+ star'>
                    <i class="fas fa-star"></i>
                </span>
                <span v-for='emptyStar in (5 - laptop.rating)' :key='"e-star: " + emptyStar'>
                    <i class="far fa-star"></i>
                </span>
            </p>
        </div>
        <div class='laptop-image'>
            <img :src='laptop.imageUrl' 
                :alt='laptop.model' 
                width='150' 
                class='d-flex align-self-center'>
        </div>
        <div class="card-body text-center">
            <button class="btn btn-outline-dark btn-lg">View Laptop Details</button>
        </div>
    </div>
</template>

<script>
export default {
    name: 'laptop',
    props: {
        laptop: Object
    },
    methods: {
        convertToUsdFormat: function (num) {
            const formatter = new Intl.NumberFormat('en-US', {
                style: 'currency',
                currency: 'USD'
            });

            return formatter.format(num);
        }
    }
}
</script>

<style>
.laptop-container {
    height: 100%;
}

.laptop-info {
    height: 40%;
}

.laptop-title {
    height: 25%;
}

.laptop-image {
    height: 25%;
    display: flex;
    justify-content: center;
    align-items: center;
}
</style>
