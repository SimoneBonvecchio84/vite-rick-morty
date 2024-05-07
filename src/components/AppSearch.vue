<script>
import { store } from "../store";
export default {
    data() {
        return {
            store,
            status: ["Alive", "Dead", "Unknown"],
        }
    }
}
</script>

<template>
   <select @change="$emit('filter')" v-model="store.selectedStatus" >
        <option :value="status" v-for="curStatus in status">
            {{ curStatus }}
        </option>
   </select>
</template>