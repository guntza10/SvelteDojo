<script></script>

<div class="card">
  <!-- slot จะเอาทุก element ที่ไม่มี attribute slot มา render -->
  <slot />
  <!-- เอา slot name buttonSlot มา render -->
  <slot name="buttonSlot" />
</div>

<style>
  .card {
    padding: 12px;
    border: 2px solid gray;
    margin-bottom: 8px;
  }
</style>
