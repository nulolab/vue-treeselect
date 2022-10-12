<template>
  <table class="striped">
    <thead>
      <tr>
        <th class="name">Name</th>
        <th>Props</th>
        <th class="desc">说明</th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="slot in slots" :key="slot.name">
        <td><strong>{{ slot.name }}</strong></td>
        <td v-html="slot.props" />
        <td v-html="slot.description" />
      </tr>
    </tbody>
  </table>
</template>

<script>
  import { link, makePropList } from './utils'

  export default {
    data: () => ({
      slots: [ {
        name: 'option-label',
        props: makePropList([ 'node', 'shouldShowCount', 'count', 'labelClassName', 'countClassName' ]),
        description: `自定义选项标签模板的插槽。有关详细信息，请参阅 ${link('#customize-option-label')}`,
      }, {
        name: 'value-label',
        props: makePropList([ 'node' ]),
        description: `自定义值标签模板的插槽。有关详细信息，请参阅 ${link('#customize-value-label')}`,
      }, {
        name: 'before-list',
        props: '-',
        description: `插槽显示在菜单列表之前`,
      }, {
        name: 'after-list',
        props: '-',
        description: `插槽显示在菜单列表之后`,
      } ],
    }),
  }
</script>
