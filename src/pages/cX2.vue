<template>
  <div>
    <q-splitter v-model="splitterModel" style="height: 400px">
      <template v-slot:before>
        <div class="q-pa-md">
          <q-tree
            :nodes="nodes"
            node-key="label"
            selected-color="primary"
            v-model:selected="selected"
            default-expand-all
            @click="onNodeSelected"
          />
        </div>
      </template>

      <template v-slot:separator>
        <q-avatar
          color="primary"
          text-color="white"
          size="40px"
          icon="drag_indicator"
        />
      </template>

      <template v-slot:after>
        <div class="col-8">
          <!-- <q-table
            :data="tableData"
            :columns="tableColumns"
            :rows-per-page-options="[10]"
          /> -->
        </div>
      </template>
    </q-splitter>
  </div>
</template>

<script>
import { ref } from 'vue';

export default {
  setup() {
    return {
      splitterModel: ref(20),
      selected: ref('Food'),
      currentContent: '',
      items: ['1', '2'],

      nodes: [
        {
          label: 'Node 1',
          children: [
            { label: 'Child 1-1', data: { name: 'Child 1-1', value: 10 } },
            { label: 'Child 1-2', data: { name: 'Child 1-2', value: 20 } },
            { label: 'Child 1-3', data: { name: 'Child 1-3', value: 30 } },
          ],
        },
        {
          label: 'Node 2',
          children: [
            { label: 'Child 2-1', data: { name: 'Child 2-1', value: 40 } },
            { label: 'Child 2-2', data: { name: 'Child 2-2', value: 50 } },
            { label: 'Child 2-3', data: { name: 'Child 2-3', value: 60 } },
          ],
        },
      ],
      tableColumns: [
        { name: 'name', align: 'left', label: 'Name', field: 'name' },
        { name: 'value', align: 'right', label: 'Value', field: 'value' },
      ],
      tableData: [],
    };
  },
  methods: {
    onNodeSelected(node) {
      console.log('ff:', node);
      this.tableData = node.data ? [node.data] : [];
    },
  },
};
</script>
