<template>
    <div class="container w-50">
        <h2>Limit Message</h2>
        <div class="input-group">
            <div class="input-group-prepend">
            <span class="input-group-Text" v-text="max-messages-length"></span>
            </div>
            <input type="text" class="form-control" v-model="messages" :maxlength="max">
    </div>
    </div>
</template>
<script>
export default {
    data() {
        return {
            messages:"",
            max:20
        }
    },
}
</script>