<script>
  // with reactive value with props
  // export let count;
  // export let average;

  // with access directly store
  import { FeedbackStore } from "../store";
  $: count = $FeedbackStore.length;
  $: average =
    $FeedbackStore.reduce((prev, current) => prev + current.rating, 0) / count;
</script>

<div class="feedback-stats">
  <h4>{count} Reviews</h4>
  <h4>Rating Average: {average}</h4>
</div>

<style>
  .feedback-stats {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
</style>
