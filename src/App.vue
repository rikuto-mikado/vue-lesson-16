<!-- Template section: Defines the HTML structure and layout of the component -->
<template>
  <section>
    <h2>My Friends</h2>
    <ul>
      <friend-contact></friend-contact>
      <friend-contact></friend-contact>
    </ul>
  </section>
</template>

<!-- Script section: Contains the component's logic, data, methods, and configuration -->
<script>
// Alternative way: const app = {...}; export default app;
// But directly using "export default" is simpler and more common
export default {
    data() {
        return {
            friends: [
                {
                    id: 'rikuto',
                    name: 'Rikuto Mikado',
                    phone: '0123-45678-90',
                    email: 'rikuto@example.com',
                },
                {
                    id: 'jun',
                    name: 'Jun Sato',
                    phone: '0987-65432-10',
                    email: 'jun@example.com',
                }
            ]
        }
    },
    methods: {

    },
};
</script>

<!-- Style section: Defines the CSS styles for this component -->
<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>