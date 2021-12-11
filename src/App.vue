<script setup>
const cursorsByCategory = [
  {
    category: 'General',
    cursors: ['auto', 'default', 'none'],
  },
  {
    category: 'Links & statuses',
    cursors: ['context-menu', 'help', 'pointer', 'progress', 'wait'],
  },
  {
    category: 'Selection',
    cursors: ['cell', 'crosshair', 'text', 'vertical-text'],
  },
  {
    category: 'Drag & drop',
    cursors: [
      'alias',
      'copy',
      'move',
      'no-drop',
      'not-allowed',
      'grab',
      'grabbing',
    ],
  },
  {
    category: 'Resize & scrolling',
    cursors: [
      'all-scroll',
      'col-resize',
      'row-resize',
      'n-resize',
      'e-resize',
      's-resize',
      'w-resize',
      'ne-resize',
      'nw-resize',
      'se-resize',
      'sw-resize',
      'ew-resize',
      'ns-resize',
      'nesw-resize',
      'nwse-resize',
    ],
  },
  {
    category: 'Zooming',
    cursors: ['zoom-in', 'zoom-out'],
  },
]
</script>

<template>
  <h1>CSS Cursors</h1>

  <ul>
    <li
      v-for="category in cursorsByCategory"
      :key="category.category"
      class="cursor-category"
    >
      <h2>{{ category.category }}</h2>
      <ul class="cursor-list">
        <li v-for="cursor in category.cursors" :key="cursor" class="cursor-item" :style="{
          '--cursor-property': cursor
        }">
          {{ cursor }}
        </li>
      </ul>
    </li>
  </ul>
</template>

<style>
.cursor-category {
  padding: 1rem;
}

.cursor-list {
  display: flex;
  flex-wrap: wrap;
  gap: 0.5rem;
}

.cursor-item {
  border: 1px solid #0004;
  
  width: 8rem;
  height: 8rem;
  display: flex;
  justify-content: center;
  align-items: center;

  cursor: var(--cursor-property)
}
</style>
