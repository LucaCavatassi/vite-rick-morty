<script>
    export default {
        data() {
            return{
                optionsArray: ["Alive", "Dead", "Unknown"]
            }
        }

    }

</script>

<template>
    <div class="form-floating px-1 mb-5">
        <select class="form-select" id="selectStatus" aria-label="select-status">
            <option v-for="curStatus in optionsArray" :value="curStatus">{{curStatus}}</option>
        </select>
    <label for="selectStatus">Select the status</label>
    </div>
</template>

<style>
</style>