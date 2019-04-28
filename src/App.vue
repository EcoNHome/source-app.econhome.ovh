<template lang="html">
    <div class="">
        <nav class="navbar navbar-expand-md navbar-dark bg-dark mb-4">
            <a class="navbar-brand" href="#">EcoN'Home</a>
            <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarCollapse" aria-controls="navbarCollapse" aria-expanded="false" aria-label="Toggle navigation">
                <span class="navbar-toggler-icon"></span>
            </button>
            <div class="collapse navbar-collapse" id="navbarCollapse">
                <ul class="navbar-nav mr-auto">
                    <li class="nav-item">
                        <router-link class="nav-link" to="/">Accueil</router-link>
                    </li>
                    <li class="nav-item">
                        <router-link class="nav-link" to="/manage">Gérer</router-link>
                    </li>
                    <li class="nav-item">
                        <router-link class="nav-link" to="/monitor">Monitorer</router-link>
                    </li>
                </ul>
                <div class="dropdown">
                    <button class="btn btn-secondary dropdown-toggle" type="button" id="dropdownMenuButton" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
                        Lucas
                    </button>
                    <div class="dropdown-menu dropdown-menu-right" aria-labelledby="dropdownMenuButton">
                        <a class="dropdown-item" href="#">Paramètres</a>
                        <a class="dropdown-item" href="#">Se Déconnecter</a>
                    </div>
                </div>
            </div>
        </nav>
        <router-view />
    </div>
</template>

<script>
export default {
    name: 'app'
}

// TODO: tester sur un cookie de stockage/localstorage est present avec un token disponible et verifier avec le backend nodejs qu'il correspond bien  un utilisateur

</script>

<style lang="css" scoped>
</style>
