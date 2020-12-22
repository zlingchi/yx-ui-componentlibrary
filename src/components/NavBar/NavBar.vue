<template>
    <nav class="NavBar">
        <NavBarItem title="Home" />
        <NavBarItem title="About" />
        <NavBarDropDown title="Services" :items="services" />
        <NavBarItem title="Contact" />
    </nav>
</template>

<script>
import NavBarDropDown from './NavBarDropDown'
import NavBarItem from './NavBarItem'

export default {
    name: 'navbar',
    components: {
        NavBarDropDown,
        NavBarItem
    },
    data () {
        return {
            services: [
                {
                    title: 'Web',
                    link: '#',
                },
                {
                    title: 'Design',
                    link: '#',
                },
                {
                    title: 'Videos',
                    link: '#',
                },              
            ]
        }
    }
}
</script>

<style>

.NavBar {
    display: flex;
    align-items: center;
    justify-content: center;
    background-color: skyblue;
}

nav .menu-item {
    color: #fff;
    padding: 10px 20px;
    position: relative;
    text-align: center;
    border-bottom: 3px solid transparent;
    display: flex;
    transition: 0.4s;
}

nav .menu-item.active, nav .menu-item:hover {
    color: rgb(59, 113, 136);
    border-bottom-color: rgb(59, 113, 136);
}

nav .menu-item a {
    color: inherit;
    text-decoration: none;
}
</style>