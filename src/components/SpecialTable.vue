<template>
    <Table :columns="propsData.header" class="specialtable" size="middle" />
    <a-collapse v-model:activeKey="activeKey" accordion>
        <a-collapse-panel class="datatable" v-for="(item, index) in propsData.dataSource" :key="String(index)"
            :header="item.group">
            <Table :columns="propsData.header" :showHeader="false" :data-source="item.dataItem" :pagination="false" />
        </a-collapse-panel>
    </a-collapse>
</template>
<script setup lang="ts">
import { ref } from 'vue'
import { Table, Collapse } from 'ant-design-vue';
const activeKey = ref<string>('1')
type dataSourceItem<T> = {
    group: string,
    dataItem: T[]
}
interface propData<T> {
    header: any[];
    pretend: boolean;
    dataSource: dataSourceItem<T>[]
}
interface columnstype {
    name: string
    age: number
    address: string
}
const dataSource = [{
    group: "test1",
    dataItem: [{
        name: 1111,
        age: 20,
        address: 'shijai jja xona w'
    },{
        name: 1111,
        age: 20,
        address: 'shijai jja xona w'
    },{
        name: 1111,
        age: 20,
        address: 'shijai jja xona w'
    },{
        name: 1111,
        age: 20,
        address: 'shijai jja xona w'
    },{
        name: 1111,
        age: 20,
        address: 'shijai jja xona w'
    }]
},{
    group: "test1",
    dataItem: [{
        name: 1111,
        age: 20,
        address: 'shijai jja xona w'
    },{
        name: 1111,
        age: 20,
        address: 'shijai jja xona w'
    },{
        name: 1111,
        age: 20,
        address: 'shijai jja xona w'
    },{
        name: 1111,
        age: 20,
        address: 'shijai jja xona w'
    },{
        name: 1111,
        age: 20,
        address: 'shijai jja xona w'
    }]
},{
    group: "test1",
    dataItem: [{
        name: 1111,
        age: 20,
        address: 'shijai jja xona w'
    },{
        name: 1111,
        age: 20,
        address: 'shijai jja xona w'
    },{
        name: 1111,
        age: 20,
        address: 'shijai jja xona w'
    },{
        name: 1111,
        age: 20,
        address: 'shijai jja xona w'
    },{
        name: 1111,
        age: 20,
        address: 'shijai jja xona w'
    }]
}]
const propsData = {
    header: [
    {
        title: '姓名',
        dataIndex: 'name',
        key: 'name',
        width: "30%"
    },
    {
        title: '年龄',
        dataIndex: 'age',
        key: 'age',
        width: "30%"
    },
    {
        title: '住址',
        dataIndex: 'address',
        key: 'address',
        width: "30%"
    }],
    pretend: false,
    dataSource: dataSource
}

</script>

<style lang="less">
.specialtable {
    .ant-table-tbody {
        display: none;
    }
}

.datatable {
    .ant-collapse-content-box {
        padding: 0 !important;
    }
}
</style>
