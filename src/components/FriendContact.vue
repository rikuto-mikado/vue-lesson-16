<template>
  <li>
    <h2>{{ friend.name }}</h2>
    <button @click="toggleDetails">Show Details</button>
    <!-- v-if: Removes element from DOM when false. Alternative: v-show (toggles CSS display property) -->
    <ul v-if="detailsVisible">
        <li><strong>Phone: </strong>{{ friend.phone }}</li>
        <li><strong>Email: </strong>{{ friend.email }}</li>
    </ul>
  </li>
</template>

<script>
export default {
    data() {
        return {
            detailsVisible: false,
            friend: {
                id: 'rikuto',
                name: 'Rikuto Mikado',
                phone: '0123-45678-90',
                email: 'rikuto@example.com',
            }
        };
    },
    methods: {
        toggleDetails() {
            this.detailsVisible = !this.detailsVisible;
        }
    }
};
</script>

