<template>
    <section class="section section--normal">


            <h2 class="title title--centered title__main--lighter" id="portfolio">
                Portfolio
            </h2>

            <br>

            <slot></slot>

            <div class="portfolio">
                <div v-for="(project, index) in projects" class="portfolio__project">
                    <img @click="openModel(index, $event)" :src="project.logo" :alt="project.name">

                    <!-- Modal Box starts here -->
                    <div v-if="showModel == true && clickedModalIndex == index" class="modal is-active">
                        <div @click="closeModel" class="modal-background"></div>
                        <div class="modal-content">
                            <div class="box has-text-left">
                                <h1 class="title title--centered title__main--lighter">{{ project.name }}</h1>

                                <p class="image">
                                    <img :src="project.imagePath" :alt="project.name">
                                </p>

                                <p>{{ project.description }}</p>

                                <p>Website: <a target="_blank" :href="project.websiteURL">{{ project.website
                                                                                          }}</a></p>
                            </div>
                        </div>
                        <button class="modal-close" @click="closeModel"></button>
                    </div>
                    <!-- Modal Box ends here -->
                </div>
            </div>

            <!--<div class="columns">-->
                <!--<div class="column is-10 is-offset-1 has-text-centered">-->

                    <!--<div class="columns">-->

                        <!--<slot></slot>-->

                        <!--<div v-for="(project, index) in projects" class="column is-4 is-6-tablet-only">-->
                            <!--<div @click="openModel(index, $event)" class="card">-->
                                <!--<div class="card-image">-->
                                    <!--<figure class="image">-->
                                        <!--<img :src="project.imagePath" :alt="project.name">-->
                                    <!--</figure>-->
                                <!--</div>-->
                            <!--</div>-->

                            <!--<div v-if="showModel == true && clickedModalIndex == index" class="modal is-active">-->
                                <!--<div @click="closeModel" class="modal-background"></div>-->
                                <!--<div class="modal-content">-->
                                    <!--<div class="box has-text-left">-->
                                        <!--<p class="image">-->
                                            <!--<img :src="project.imagePath" :alt="project.name">-->
                                        <!--</p>-->

                                        <!--<h1>{{ project.name }}</h1>-->
                                        <!--<p>{{ project.description }}</p>-->

                                        <!--<p>Website: <a target="_blank" :href="project.websiteURL">{{ project.website-->
                                                                                                  <!--}}</a></p>-->
                                    <!--</div>-->
                                <!--</div>-->
                                <!--<button class="modal-close" @click="closeModel"></button>-->
                            <!--</div>-->
                        <!--</div>-->
                    <!--</div>-->
                <!--</div>-->
            <!--</div>-->

    </section>
</template>

<style lang="scss">

    .modal {
        h1 {
            font-size : 22px;
            margin    : 3% auto 1% auto;
        }
    }

    @media (max-width : 768px) {
        .card {
            margin : auto;
        }
    }
</style>

<script>
    import Project from './Project.vue';

    export default{
        data(){
            return{
                projects: [], showModel: false, clickedModalIndex: 0
            }
        },

        created() {
            this.projects = this.$children;
        },

        methods: {
            openModel: function(index){
                this.showModel = true;
                this.clickedModalIndex = index;
            },

            closeModel: function() {
                this.showModel = false;
            }
        }
    }

</script>
