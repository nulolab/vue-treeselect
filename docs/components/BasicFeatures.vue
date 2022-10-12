<template>
  <div>
    <treeselect
      :multiple="true"
      :options="options"
      placeholder="选择您最喜爱的..."
      v-model="value"
      />
    <treeselect-value :value="value" />
  </div>
</template>

<script>
  export default {
    data: () => ({
      value: [],
      options: [ {
        id: 'fruits',
        label: '水果',
        children: [ {
          id: 'apple',
          label: '苹果 🍎',
          isNew: true,
        }, {
          id: 'grapes',
          label: '葡萄 🍇',
        }, {
          id: 'pear',
          label: '梨子 🍐',
        }, {
          id: 'strawberry',
          label: '草莓 🍓',
        }, {
          id: 'watermelon',
          label: '西瓜 🍉',
        } ],
      }, {
        id: 'vegetables',
        label: '蔬菜',
        children: [ {
          id: 'corn',
          label: '玉米 🌽',
        }, {
          id: 'carrot',
          label: '胡萝卜 🥕',
        }, {
          id: 'eggplant',
          label: '茄子 🍆',
        }, {
          id: 'tomato',
          label: '番茄 🍅',
        } ],
      }, {
        id: 'noChildren',
        label: '无子选项',
        children: [],
      } ],
    }),
  }
</script>
