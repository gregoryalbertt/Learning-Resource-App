<template>
    <base-card>
        <form @submit.prevent="submitResource">
            <div class="form-control">
                <label>Title</label>
                <input type="text" placeholder="Title" v-model="resource.title">
            </div>
            <div class="form-control">
                <label>Description</label>
                <textarea name="" id="description" cols="30" rows="3" placeholder="Description"
                    v-model="resource.description"></textarea>
            </div>
            <div class="form-control">
                <label>Link</label>
                <input type="url" placeholder="Link" v-model="resource.link">
            </div>
            <base-button type="submit">Add Resource</base-button>
        </form>
    </base-card>
</template>

<script>
export default {
    data() {
        return {
            resource: {
                title: '',
                description: '',
                link: '',
            },
        }
    },
    methods: {
        submitResource() {
            // this.$emit('addResource', this.resource);
            this.addResource(this.resource)
            this.resource = {}
        }
    },
    inject: ['addResource'],
}
</script>

<style scoped>
label {
    font-weight: bold;
    display: block;
    margin-bottom: 0.5rem;
}

input,
textarea {
    display: block;
    width: 100%;
    font: inherit;
    padding: 0.15rem;
    border: 1px solid #ccc;
}

input:focus,
textarea:focus {
    outline: none;
    border-color: #3a0061;
    background-color: #f7ebff;
}

.form-control {
    margin: 1rem 0;
}
</style>