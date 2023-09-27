

<script>
export default {
    name: 'SearchImput',
    emits: ['performSearch']

}
</script>
<template>
    <div class="py-3">
        <select class="form-select w-25" aria-label="Default select example" @change="$emit('performSearch')">
            <option selected>Choose Archetyp</option>
            <option value="Alien">Alien</option>
            <option value="Noble Knight">Noble Knight</option>
            <option value="Tainted Treasure">Tainted Treasure</option>
            <option value="Melodious">Melodious</option>
            <option value="Archfiend">Archfiend</option>
        </select>
    </div>
</template>

<style lang="scss" scoped></style>