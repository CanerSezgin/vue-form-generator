<template>
    <div>
        <component
            :is="component"
            :element="element"
            :error="error"
        ></component>
        <v-radio-group v-model="element.type" v-if="hasType">
            <v-row no-gutters>
                <v-col cols="6">
                    <v-radio label="Regular" color="pink" value="regular"></v-radio>
                    <v-radio label="Solo" color="pink" value="solo"></v-radio>
                </v-col>
                <v-col cols="6">
                    <v-radio label="Outlined" color="pink" value="outlined"
                    ></v-radio>
                    <v-radio label="Filled" color="pink" value="filled"></v-radio>
                </v-col>
            </v-row>
        </v-radio-group>
    </div>
</template>

<script>
import SimpleText from "@/components/FormManager/AdditionalProps/static/SimpleText";

import VTextField from "@/components/FormManager/AdditionalProps/input/VTextField";
import VTextArea from "@/components/FormManager/AdditionalProps/input/VTextArea";
import VCombobox from "@/components/FormManager/AdditionalProps/input/VCombobox";
import VSelect from "@/components/FormManager/AdditionalProps/input/VSelect";
import VCheckbox from "@/components/FormManager/AdditionalProps/input/VCheckbox";
import VSwitch from "@/components/FormManager/AdditionalProps/input/VSwitch";
import VRadioButton from "@/components/FormManager/AdditionalProps/input/VRadioButton";

export default {
    components: {
        SimpleText,

        VTextField,
        VTextArea,
        VCombobox,
        VSelect,
        VCheckbox,
        VSwitch,
        VRadioButton
    },
    props: ["component", "element", "category", "error"],
    computed: {
        hasType() {
            return this.category === 'input' && 'type' in this.element
        }
    }
};
</script>
