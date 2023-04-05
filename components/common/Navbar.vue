<template>
    <div class="sticky top-5 z-50 navbar bg-base-100 text-white rounded-2xl">
        <div class="navbar-start">
            <div class="dropdown">
                <label tabindex="0" class="btn btn-ghost btn-circle">
                    <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h7" /></svg>
                </label>
                <ul tabindex="0" class="menu menu-compact dropdown-content mt-3 p-2 shadow bg-base-100 rounded-2xl w-52">
                    <li><nuxt-link>Homepage</nuxt-link></li>
                    <li><nuxt-link>Portfolio</nuxt-link></li>
                    <li><nuxt-link>About</nuxt-link></li>
                </ul>
            </div>
        </div>
        <div class="navbar-center">
            <a class="btn btn-ghost normal-case text-xl rounded">Samuel Belo</a>
        </div>
        <div class="navbar-end"></div>
    </div>
</template>

<script>
export default {
name: "Navbar"
}
</script>

<style scoped>

</style>