<!-- eslint-disable vue/no-multiple-template-root -->
<template>
    <base-card>
        <base-button @click="setSelectedTab('stored-resources')" :mode="storedResButtonMode">Stored Resources</base-button>
        <base-button @click="setSelectedTab('add-resource')" :mode="addResButtonMode">Add Resources</base-button>
    </base-card>
    <component :is="selectedTab" @addResource="addResource"></component>
</template>

<script>
import StoredResources from './StoredResources.vue';
import AddResource from './AddResource.vue';

export default {
    data() {
        return {
            selectedTab: 'stored-resources',
            storedResources: [
                {
                    id: 'official guide',
                    title: 'Official Guide',
                    description: 'The official vue.js documentation',
                    link: 'http://vuejs.org'
                },
                {
                    id: 'google',
                    title: 'Google',
                    description: 'Learn to Google...',
                    link: 'http://google.com'
                },
            ]
        };
    },
    provide() {
        return {
            resources: this.storedResources,
            addResource: this.addResource,
        }
    },
    methods: {
        setSelectedTab(tab) {
            this.selectedTab = tab;
        },
        addResource(arg) {
            this.storedResources.unshift(arg)
        }
    },
    computed: {
        storedResButtonMode() {
            return this.selectedTab === 'stored-resources' ? null : 'flat'
        },
        addResButtonMode() {
            return this.selectedTab === 'add-resource' ? null : 'flat'
        },
    },
    components: { StoredResources, AddResource }

}
</script>

<style scoped></style>