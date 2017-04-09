<template>

    <section class="section section--fullscreen">

        <h1 class="title title__main title--white">
            I'm {{ name }}
        </h1>
        <h3 class="title title__sub title__sub--border title--white">
            {{ profession }}
        </h3>

        <ul class="nav">
            <li class="nav__nav-item"><a href="#about">Who?</a></li>
            <li class="nav__nav-item"><a href="#education">Education.</a></li>
            <li class="nav__nav-item"><a href="#jobs">Jobs.</a></li>
            <li class="nav__nav-item"><a href="#portfolio">Portfolio.</a></li>
        </ul>

        <p class="image-copyright"><a href="https://www.instagram.com/onew_dude/" target="_blank">@Onew_Dude</a></p>
        <i class="fa fa-arrow-down arrow arrow--white arrow--down"></i>
    </section>

</template>

<style lang="scss">

</style>

<script>

    export default{
        data () {
            return {

            }
        },

        props: ['name', 'profession']
    }
</script>
