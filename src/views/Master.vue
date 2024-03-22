<template>
    <!-- ===== Main Container Start ===== -->
    <div class="main-container">

    <!-- ===== Aside Start ===== -->
    <div class="aside">
        <div class="logo">
            <a href="#"><span>R</span>M</a>
            <p>Begginer Web Developer</p>

        </div>

        <div class="nav-toggler">
            <span></span>
        </div>

        <ul class="nav">
            <li><a href="#home" class="active"><i class="fa fa-home"></i>Home</a></li>
            <li><a href="#about"><i class="fa fa-user"></i>About</a></li>
            <li><a href="#services"><i class="fa fa-list"></i>Service</a></li>
            <li><a href="#portfolio"><i class="fa fa-briefcase"></i>Portfolio</a></li>
            <li><a href="#contact"><i class="fa fa-comments"></i>Contact</a></li>
        </ul>
    </div>
    <!-- ===== Aside End ===== -->

    <!-- ===== Main Content Start ===== -->
    <div class="main-content">

    <!-- ===== Home Section Start ===== -->
        <home></home>
    <!-- ===== Home Section End ===== -->

    <!-- ===== About Section Start ===== -->
        <about></about>
    <!-- ===== About Section End ===== -->



    <!-- ===== Services Section Start ===== -->
        <service></service>
    <!-- ===== Services Section End ===== -->



    <!-- ===== Portfolio Section Start ===== -->
        <portfolio></portfolio>
    <!-- ===== Portfolio Section End ===== -->

    <!-- ===== Contact Section Start ===== -->
        <contact></contact>
    <!-- ===== Contact Section End ===== -->
    </div>
    <!-- ===== Main Content End ===== -->
    </div>
    <!-- ===== Main Container End ===== -->
    <!-- ===== Style Switcher Start ===== -->
    <div class="style-switcher">
    <div class="style-switcher-toggler s-icon">
        <i class="fas fa-cog fa-spin"></i>
    </div>
    <div class="day-night s-icon">
        <i class="fas"></i>
    </div>
    <h4>Theme Color</h4>
    <div class="colors">
        <span class="color-1" @click="setActiveStyle('color-1')"></span>
        <span class="color-2" @click="setActiveStyle('color-2')"></span>
        <span class="color-3" @click="setActiveStyle('color-3')"></span>
        <span class="color-4" @click="setActiveStyle('color-4')"></span>
        <span class="color-5" @click="setActiveStyle('color-5')"></span>
    </div>
    </div>
<!-- ===== Style Switcher End ===== -->
</template>

<script>
import Home from '../pages/Home.vue'
import About from '../pages/About.vue'
import Service from '../pages/Service.vue'
import Portfolio from '../pages/Portfolio.vue'
import Contact from '../pages/Contact.vue'
import { myFunction } from '../../public/frontend/js/script'
import  {switchStyles} from '../../public/frontend/js/style-switcher'
export default {
    components: {Home,About,Service,Portfolio,Contact,},
    name: 'Master',
    mounted() {
        myFunction();
        switchStyles();
    },
    
    /* ========================== theme colors ========================== */
    data() {
        return {
            colors: ['color-1', 'color-2', 'color-3', 'color-4', 'color-5'],
            currentColorIndex: 0
        };
    },

    methods: {
        setActiveStyle(color) {
            // Logic to set the active style
            const alternateStyles = document.querySelectorAll(".alternate-style");
            alternateStyles.forEach((style) => {
                if (color === style.getAttribute("title")) {
                    style.removeAttribute("disabled");
                } else {
                    style.setAttribute("disabled", "true");
                }
            });

            // Optionally, update the currentColorIndex
            this.currentColorIndex = this.colors.findIndex(c => c === color);
        }
    }
};
</script>

<style>

</style>
