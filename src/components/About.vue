<template>
    <section class="section section--normal" id="about">
        <div class="container">
            <div class="columns">
                <div class="column is-10 is-offset-1 align--center">
                    <h2 class="title title--centered title__main--lighter">
                        About me
                    </h2>
                    <p>
                        <slot></slot>
                    </p>

                    <br>

                    <a :href="resumeURL" target="_blank" class="button button--default">
                        Download my resume
                    </a>

                </div>
            </div>
        </div>
    </section>
</template>

<style>

</style>

<script>

    export default{
        data(){
            return{

            }
        },

        props: {
            resumeURL: {
                default: '#aboutSection'
            }
        }
    }
</script>
