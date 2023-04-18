<script>
import { store } from "../store"
export default {
    name: "AppBtn",
    emit: ["filter"],
    data() {
        return {
            store,
            statusArray: ["Alien", "Ally of Justice", "Ancient Gear"]
        }
    }
}
</script>

<template>
          <div class="selector">
            <div class="container d-flex justify-content-center p-4">
                <select class="form-select w-25" name="status" id="status" v-model="store.activeStatus" @change="$emit('filter')">
                    <option value="">All</option>
                    <option :value="status" v-for="status in statusArray">{{ status }}</option>
                </select>
            </div>

          </div>
</template>

<style lang="scss" scoped>
@use "../styles/variables.scss" as *;
.selector {
    height: 80px;
    background-color: $primary;
}
</style>