<template>
<div class="c-notebook__search-results">
    <div class="c-notebook__search-results__header">Search Results</div>
    <div class="c-notebook__entries">
        <NotebookEntry v-for="(result, index) in results"
                       :key="index"
                       :result="result"
                       :entry="result.entry"
                       :read-only="true"
                       :selected-page="null"
                       :selected-section="null"
                       @changeSectionPage="changeSectionPage"
        />
    </div>
</div>
</template>

<script>
import NotebookEntry from './notebook-entry.vue';

export default {
    inject: ['openmct', 'domainObject'],
    components: {
        NotebookEntry
    },
    props: {
        results: {
            type: Array,
            default() {
                return [];
            }
        }
    },
    data() {
        return {};
    },
    watch: {
        results(newResults) {}
    },
    destroyed() {
    },
    mounted() {
    },
    methods: {
        changeSectionPage(data) {
            this.$emit('changeSectionPage', data);
        }
    }
};
</script>
