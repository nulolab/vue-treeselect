<template>
  <table class="striped">
    <thead>
      <tr>
        <th class="name">事件名称</th>
        <th>回调参数</th>
        <th class="desc">说明</th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="event in events" :key="event.name">
        <td><strong>{{ event.name }}</strong></td>
        <td v-html="event.attributes" />
        <td>{{ event.description }}</td>
      </tr>
    </tbody>
  </table>
</template>

<script>
  import { makeArgNameList } from './utils'

  export default {
    data: () => ({
      events: [ {
        name: 'open',
        attributes: makeArgNameList([ 'instanceId' ]),
        description: 'menu 打开的回调',
      }, {
        name: 'close',
        attributes: makeArgNameList([ 'value', 'instanceId' ]),
        description: 'menu 关闭的回调',
      }, {
        name: 'input',
        attributes: makeArgNameList([ 'value', 'instanceId' ]),
        description: '更改 value 后触发',
      }, {
        name: 'select',
        attributes: makeArgNameList([ 'node', 'instanceId' ]),
        description: '选择 option 后触发',
      }, {
        name: 'deselect',
        attributes: makeArgNameList([ 'node', 'instanceId' ]),
        description: '取消选择 option 后触发',
      }, {
        name: 'search-change',
        attributes: makeArgNameList([ 'searchQuery', 'instanceId' ]),
        description: '搜索框值更改后触发',
      } ],
    }),
  }
</script>
