<template>
    <div>
        <div style="margin-top: 100px; margin-left: 100px; max-width: 300px;">
        <vue-treeselect
            :multiple="true"
            :options="[treeData]"
            noResultsText="No results..."
            placeholder="Select items..."
            v-model="selected"
            :appendToBody="true"
            :default-expand-level="0"
            :autoSelectDescendants="true"
            :autoDeselectDescendants="true"
            :flat="true"
            :searchable="false"
            :show-count="true"
        >
        </vue-treeselect>

        Not appended to body:
        <vue-treeselect
            :multiple="false"
            placement="bottom"
            :appendToBody="false"
            :options="[treeData]"
            noResultsText="No results..."
            placeholder="Select items..."
            v-model="selected4"
            :default-expand-level="0"
            :autoSelectDescendants="true"
            :autoDeselectDescendants="true"
            :flat="true"
            :searchable="false"
            :show-count="true"

        :open-on-click="true"
        :open-on-focus="true"
        :clear-on-select="true"
        :isDefaultExpanded="true"
        :always-open="false"
        :disabled="read_only"
        :disableFuzzyMatching="true"
        :defaultExpandLevel="expandLevel"
        class="tree-select"
        :close-on-select="true"
        :maxHeight="250"
        open-direction="auto"
        >
        </vue-treeselect>
        </div>
        <div>
            Selected: {{selected}}
        </div>

        Append to body:

        <div style="margin-top: 100px; margin-left: 100px; max-width:300px;">
        <vue-treeselect
            :multiple="false"
            :options="[treeData]"
            placement="top"
            noResultsText="No results..."
            placeholder="Select items..."
            v-model="selected2"

            :appendToBody="true"
            :default-expand-level="0"
            :autoSelectDescendants="true"
            :autoDeselectDescendants="true"
            :flat="true"
            :searchable="false"
            :show-count="true"

            :open-on-click="true"
            :open-on-focus="true"
            :clear-on-select="true"
            :isDefaultExpanded="true"
            :always-open="false"
            :disableFuzzyMatching="true"
            :defaultExpandLevel="999"
            class="tree-select"
            :close-on-select="false"
            :maxHeight="250"
            open-direction="auto"
        >
        </vue-treeselect>
        </div>

        <p>lorem ipsum dolor sit amet</p>
        <p>lorem ipsum dolor sit amet</p>
        <p>lorem ipsum dolor sit amet</p>
        <p>lorem ipsum dolor sit amet</p>
        <p>lorem ipsum dolor sit amet</p>
        <p>lorem ipsum dolor sit amet</p>
        <p>lorem ipsum dolor sit amet</p>
        <p>lorem ipsum dolor sit amet</p>
        <p>lorem ipsum dolor sit amet</p>
        <p>lorem ipsum dolor sit amet</p>
        <p>lorem ipsum dolor sit amet</p>
        <p>lorem ipsum dolor sit amet</p>
        <p>lorem ipsum dolor sit amet</p>
        <div style="margin-top: 100px; margin-left: 100px; max-width:300px;">
        <vue-treeselect
            :multiple="true"
            :options="[treeData]"
            placement="top"
            noResultsText="No results..."
            placeholder="Select items..."
            v-model="selected3"

            :appendToBody="true"
            :default-expand-level="0"
            :autoSelectDescendants="true"
            :autoDeselectDescendants="true"
            :flat="true"
            :searchable="false"
            :show-count="true"

            :open-on-click="true"
            :open-on-focus="true"
            :clear-on-select="true"
            :isDefaultExpanded="true"
            :always-open="false"
            :disableFuzzyMatching="true"
            :defaultExpandLevel="999"
            class="tree-select"
            :close-on-select="false"
            :maxHeight="250"
            open-direction="auto"
        >
        </vue-treeselect>
        </div>
        <p>lorem ipsum dolor sit amet</p>
        <p>lorem ipsum dolor sit amet</p>
        <p>lorem ipsum dolor sit amet</p>
        <p>lorem ipsum dolor sit amet</p>
        <p>lorem ipsum dolor sit amet</p>
        <p>lorem ipsum dolor sit amet</p>
        <p>lorem ipsum dolor sit amet</p>

    </div>
</template>
<script>
import { defineComponent,ref,reactive } from 'vue';

export default defineComponent({

    setup() {

        let selected = ref([2,1]);
        let selected2 = ref([]);
        let selected3 = ref([]);
        let selected4 = ref([]);
        let treeOrientation = ref("0");
        let treeData = reactive({
            label: 'root',
            expand: true,
            id: 1,
            children: [
                { label: 'child 1', id: 2, },
                { label: 'child 2', id: 3, },
                { 
                    label: 'subparent 1', 
                    id: 4, 
                    expand: false, 
                    isUnselectable: true,
                    children: [
                        { label: 'subchild 1', id: 5 },
                        {  
                            label: 'subchild 2', 
                            id: 6, 
                            expand: false, 
                            children: [
                                { label: 'subchild 11', id: 7 },
                                { label: 'subchild 11', id: 8 },
                                { label: 'subchild 11', id: 9 },
                                { label: 'subchild 11', id: 10 },
                                { label: 'subchild 11', id: 11 },
                                { label: 'subchild 11', id: 12 },
                                { label: 'subchild 11', id: 13 },
                                { label: 'subchild 11', id: 14 },
                                { label: 'subchild 11', id: 15 },
                                { label: 'subchild 22', id: 16 },
                            ]
                        },
                    ]
                },
            ]
        });


        return {
            treeData,
            selected,
            selected2,
            selected3,
            selected4,
        }
    }
})

</script>
