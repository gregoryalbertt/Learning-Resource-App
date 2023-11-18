<!-- eslint-disable vue/no-multiple-template-root -->
/* eslint-disable */
<template>
    <TheHeader :title="title"></TheHeader>
    <StoredResources :resources="storedResources"></StoredResources>
</template>

<script>
import TheHeader from './components/layouts/TheHeader.vue';
import StoredResources from './components/learning-resources/StoredResources.vue';


export default {
    data() {
        return {
            title: 'Learning App Resources',
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
    components: { StoredResources, TheHeader }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap');

* {
    box-sizing: border-box;
}

html {
    font-family: 'Roboto', sans-serif;
}

body {
    margin: 0;
}
</style>