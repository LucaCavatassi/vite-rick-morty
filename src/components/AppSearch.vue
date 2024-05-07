<script>
import {store} from "../store"

    export default {
        data() {
            return{
                store,
                optionsArray: ["All","Alive", "Dead", "Unknown"]
            }
        }

    }

</script>

<template>
    <div class="form-floating px-1 mb-5">
        <select @change="$emit('filter')" class="form-select" id="selectStatus" aria-label="select-status" v-model="store.selectedStatus">
            <option v-for="curStatus in optionsArray" :value="curStatus">{{curStatus}}</option>
        </select>
    <label for="selectStatus">Select the status</label>
    </div>
</template>

<style>
</style>