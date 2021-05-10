<template>
    <div id="app" class="container">
        <h1 class="mb-4">Un quiz ?</h1>
        <b-card
            header="Quel révolutionnaire et grand orateur a déclaré en 1792 : “De l’audace, encore de l’audace, toujours de l’audace.”"
            header-tag="header">
            <b-list-group>
                <b-list-group-item button>Desmoulin</b-list-group-item>
                <b-list-group-item button>Danton</b-list-group-item>
                <b-list-group-item button>Robespierre</b-list-group-item>
                <b-list-group-item button>Saint Just</b-list-group-item>
            </b-list-group>
        </b-card>
    </div>
</template>

<script>
export default {
    name: "App",
};
</script>

<style>
#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
}
</style>
