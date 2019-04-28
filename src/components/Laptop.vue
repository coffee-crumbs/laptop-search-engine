<template>
    <tr>
        <td class='laptop-select-col'>
        <input type="checkbox">
        </td>
        <td class='laptop-col'>
        <img src="../assets/img-placeholder.jpg" alt="image-placeholder">
        <span>{{ laptop.model }}</span>
        </td>
        <td class='laptop-rating-col'>{{ '*'.repeat(laptop.rating) }} ({{ laptop.numOfReviews }})</td>
        <td class='laptop-price-col'>{{ this.convertToUsdFormat(laptop.price) }}</td>
        <td class='laptop-add-col'>
        <button>Add</button>
        </td>
    </tr>
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
.laptop-col img {
  width: 3em;
}

.laptop-col {
  display: flex;
  align-items: center;
  justify-content: space-evenly;
  padding: 1em 0;
}
</style>
