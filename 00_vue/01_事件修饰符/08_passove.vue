<!-- 滚动事件的默认行为 (即滚动行为) 将会立即触发 --> 
<!-- 而不会等待 `onScroll` 完成 --> 
<!-- 这其中包含 `event.preventDefault()` 的情况 --> 

<div v-on:scroll.passive="onScroll">...</div>

