<script>
import { store } from "../store";
export default {
    data() {
        return {
            store,
            status: ["All", "Alive", "Dead", "Unknown"],
        }
    }
}
</script>

<template>
    <div class="container">
        <div class="d-flex justify-content-between">
            <div>
                <select @change="$emit('filter')" v-model="store.selectedStatus">
                     <option  :value="curStatus" v-for="curStatus in status">
                         {{ curStatus }}
                     </option>                 
                </select>
            </div>
        </div>
        <p>Mostrati {{ store.listsStCards.length }}</p>
    </div>
</template>