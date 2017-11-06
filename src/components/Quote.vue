<template>
  <div class="w3-container w3-third">

    <div class="w3-panel w3-card-4 w3-round-large w3-cyan">
      <!-- Slot to output 'quotes' -->
      <slot></slot>
    </div>

  </div>
</template>

<style>
  .w3-panel {
      font-family: 'Love Ya Like A Sister', cursive;
      font-size: 24px;
      padding: 20px;
      color: white !important;
      word-wrap: break-word;
  }

  .w3-panel:hover {
    cursor: pointer;
    color: maroon !important;
    background-color: #ffe1dd !important;
  }
</style>
