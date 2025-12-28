<template>
  <li>
    <h2>{{ name }}</h2>
    <button @click="toggleDetails">{{ detailsVisible ? 'Hide' : 'Show' }} Details</button>
    <!-- v-if: Removes element from DOM when false. Alternative: v-show (toggles CSS display property) -->
    <ul v-if="detailsVisible">
        <li><strong>Phone: </strong>{{ phoneNumber }}</li>
        <li><strong>Email: </strong>{{ emailAdress }}</li>
    </ul>
  </li>
</template>

<script>
export default {
    // Array syntax for props: Simple and concise, but no type validation.
    // Alternative: Object syntax with type checking: props: { name: String, phoneNumber: String, emailAdress: String }
    props: [
        'name', 
        'phoneNumber', 
        'emailAdress'
    ],
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

