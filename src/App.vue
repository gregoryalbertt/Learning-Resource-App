<template>
    <ul>
        <li v-for="resource in storedResources">{{ resource }}</li>
    </ul>
</template>

<script>
export default {
    data() {
        return {
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
                    description: 'Learn to Google',
                    link: 'http://google.com'
                },
            ]
        }
    }

}
</script>

<style></style>