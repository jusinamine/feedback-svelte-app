<script>
  import { FeedbackStore } from "../stores";

  $: count = $FeedbackStore.length;
  $: average = $FeedbackStore.reduce(
    (a, { rating }) => a + rating / $FeedbackStore.length,
    0
  );
</script>

<div class="facebook-stats">
  <h4>{count} Reviews</h4>
  <h4>Ratings Average: {average}</h4>
</div>

<style>
  .facebook-stats {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
</style>
