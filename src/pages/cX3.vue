<template>
  <div class="q-pa-md">
    <q-tree
      :nodes="nodes"
      :options="{ static: true }"
      v-model:selected="selectedNode"
    />
    <q-table
      :data="tableData"
      :columns="tableColumns"
      :pagination="false"
      :rows-per-page-options="[10]"
    />
  </div>
</template>

<script>
export default {
  data() {
    return {
      nodes: [
        {
          label: 'Node 1',
          data: { name: 'Node 1', value: 100 },
          clickable: true,
          children: [
            {
              label: 'Child 1-1',
              data: { name: 'Child 1-1', value: 10 },
              clickable: true,
            },
            {
              label: 'Child 1-2',
              data: { name: 'Child 1-2', value: 20 },
              clickable: true,
            },
            {
              label: 'Child 1-3',
              data: { name: 'Child 1-3', value: 30 },
              clickable: true,
            },
          ],
        },
        {
          label: 'Node 2',
          data: { name: 'Node 2', value: 200 },
          clickable: true,
          children: [
            {
              label: 'Child 2-1',
              data: { name: 'Child 2-1', value: 40 },
              clickable: true,
            },
            {
              label: 'Child 2-2',
              data: { name: 'Child 2-2', value: 50 },
              clickable: true,
            },
            {
              label: 'Child 2-3',
              data: { name: 'Child 2-3', value: 60 },
              clickable: true,
            },
          ],
        },
      ],
      tableColumns: [
        { name: 'name', align: 'left', label: 'Name', field: 'name' },
        { name: 'value', align: 'right', label: 'Value', field: 'value' },
      ],
      tableData: [],
      selectedNode: null, // 绑定选中节点的数据
    };
  },
  watch: {
    selectedNode(node) {
      console.log('ff', node);
      this.tableData = node.data ? [node.data] : [];
    },
  },
};
</script>
