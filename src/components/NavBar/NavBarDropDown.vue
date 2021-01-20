<template>
    <div class="menu-item" @mouseover="isOpen = true" @mouseleave="isOpen = false">
        <a href="#">
            {{ title }}
        </a>
        <div class="triangle"></div>
        <transition name="down-menu" appear>
            <div class="sub-menu" v-if="isOpen">
                <div v-for="(item, i) in items" :key="i" class="menu-item">
                    <a :href="item.link">
                        {{ item.title }}
                    </a>   
                </div>
            </div>
        </transition>
    </div>
</template>

<script>
export default {
    name: 'YXNavBarDropDown',
    props: ['title', 'items'],
    data () {   
        return {
            isOpen: false
        }
    }
}
</script>

<style>
nav .triangle {
    width: 0;
    height: 0;
    border-style: solid;
    border-width: 5px;
    border-color: #fff transparent transparent transparent;
    margin-left: 10px;
    margin-top: 10px;
    transition: 0.4s;
}

nav .menu-item.active, nav .menu-item:hover > .triangle {
    border-color: rgb(59, 113, 136) transparent transparent transparent;
}

nav .menu-item .sub-menu {
    position: absolute;
    background-color: skyblue;
    top: calc(100% + 3px);
    left: 15%;
    width: max-content;
}
</style>