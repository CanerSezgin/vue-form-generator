<template>
<!-- So similar to VSwitch, if you make any changes, make sure you have done for the VSwitch as well -->
    <div v-if="opts">
        <v-checkbox
            class="mt-1"
            v-if="!opts.isPreview"
            v-model="opts.form[opts.key]"
            :label="opts.label"
        ></v-checkbox>

        <!-- Preview -->
        <v-checkbox
            v-if="opts.isPreview"
            :label="opts.label"
        ></v-checkbox>

    </div>

</template>

<script>
export default {
    props: ["opts"]
};
</script>

<style lang="scss" scoped></style>
