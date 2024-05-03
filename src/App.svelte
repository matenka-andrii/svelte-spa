<script>
  // Components
  import FeedbackList from './components/FeedbackList.svelte';
  import FeedbackStats from './components/FeedbackStats.svelte';
  import FeedbackFrom from './components/FeedbackFrom.svelte';

  // Like a props
  // $: count = feedback.length;
  // $: average = feedback.reduce((a, { rating }) => a + rating, 0) / feedback.length;

  // const addFeedback = (e) => {
  //   const newFeedback = e.detail;
  //   feedback = [newFeedback, ...feedback];
  // };
  // const deleteFeedback = (e) => {
  //   const itemId = e.detail;
  //
  //   feedback = feedback.filter(o => o.id !== itemId);
  // };
</script>

<main class="container">
  <FeedbackFrom/> <!-- on:add-feedback={addFeedback} -->
  <FeedbackStats /> <!-- props {count} {average} -->
  <FeedbackList /> <!-- on:delete-feedback={deleteFeedback} -->
</main>