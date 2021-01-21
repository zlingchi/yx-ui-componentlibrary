<!--
 * @Author: your name
 * @Date: 2020-12-21 17:04:13
 * @LastEditTime: 2021-01-20 15:40:50
 * @LastEditors: Please set LastEditors
 * @Description: In User Settings Edit
 * @FilePath: \yx-ui-componentlibrary\src\components\navBar\navBar.vue
-->
<template>
    <nav class="yx-navBar">
        <YXNavBarItem title="Home" />
        <YXNavBarItem title="About" />
        <YXNavBarDropDown title="Services" :items="services" />
        <YXNavBarItem title="Contact" />
    </nav>
</template>

<script>
import YXNavBarDropDown from './navBarDropDown'
import YXNavBarItem from './navBarItem'

export default {
    name: 'YXNavBar',
    components: {
        YXNavBarDropDown,
        YXNavBarItem
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

.yx-navBar {
    display: flex;
    align-items: center;
    justify-content: center;
    background-color: skyblue;
    -moz-user-select: none;
    -webkit-user-select: none;
    -ms-user-select: none;
}

.yx-navBar .menu-item {
    color: #fff;
    padding: 10px 20px;
    position: relative;
    text-align: center;
    border-bottom: 3px solid transparent;
    display: flex;
    transition: 0.4s;
}

.yx-navBar .menu-item.active, nav .menu-item:hover {
    color: rgb(59, 113, 136);
    border-bottom-color: rgb(59, 113, 136);
}

.yx-navBar .menu-item a {
    color: inherit;
    text-decoration: none;
}
</style>