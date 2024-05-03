<script>
    // Store
    import { FeedbackStore } from '../store/index.js';

    // Use export to get a props
    // export let count;
    // export let average;

    $: count = $FeedbackStore.length;
    $: average = $FeedbackStore.reduce((a, { rating }) => a + rating, 0) / $FeedbackStore.length;
</script>

<div class="feedback-stats">
    <h4>{ count } Reviews</h4>
    <h4>Ratings Average: { average }</h4>
</div>

<style>
    .feedback-stats {
        display: flex;
        justify-content: space-between;
        align-items: center;
    }
</style>