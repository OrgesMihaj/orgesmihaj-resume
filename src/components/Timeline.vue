<template>
    <section class="section section--gray">
        <div class="container">
            <div class="columns">
                <div class="column is-10 is-12-mobile is-offset-1">
                    <h2 class="title title--centered title__main--lighter" :id="id">
                        {{ name }}
                    </h2>

                    <div class="timeline is-relative">
                        <div class="tl-line is-hidden-mobile"></div>

                        <div v-for="(record, index) in records"
                             :class="(index % 2 == 0) ? 'tlLeft' : 'tlRight'"
                             :style="index == 1 ? 'margin-top: 4em' : ''"
                             class="is-halfwidth and is-fullwidth-mobile"
                        >
                            <div class="boxInner">
                                <div class="dot is-hidden-mobile"></div>

                                <div class="card-content">
                                    <div class="content">
                                        <h3 v-if="record.role">{{ record.role }}</h3>
                                        <h3 v-else>{{ record.institution }}</h3>

                                        <p>{{ record.description }}
                                            <a v-if="record.employer" target="_blank" :href="record.employerURL">#{{ record.employer }}</a>
                                            <a v-else target="_blank" :href="record.websiteURL">{{ record.website }}</a>
                                        </p>
                                        <small>{{ record.period }}</small>
                                    </div>
                                </div>
                            </div>
                        </div>

                        <slot></slot>
                    </div>

                </div>
            </div>

        </div>
    </section>
</template>



<script>
    import Record from './Record.vue';

    export default {

        data(){
            return{
                records: []
            };
        },

        created() {
            this.records = this.$children;
        },


        props: ['name', 'id']
    }

</script>

<style lang="scss">

    @media (max-width: 768px) {
        .tlRight {
            margin-top: 0 !important;
        }

        .boxInner {
            padding: 0;
            margin-right: 0 !important;
            margin-left: 0 !important;

            &:after, &:before {
                display: none;
            }
        }
    }

</style>