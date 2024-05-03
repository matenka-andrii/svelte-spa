<script>
    // Core
    // import { onDestroy } from 'svelte';
    import { fade, scale } from 'svelte/transition';

    // Components
    import FeedbackItem from './FeedbackItem.svelte';

    // Store
    import { FeedbackStore } from '../store';

    // let feedback = [];
    // const unsubscribe = FeedbackStore.subscribe((data) => feedback = data);
    // onDestroy(() => {
    //     unsubscribe();
    // });
</script>

{#each $FeedbackStore as fb (fb.id)}
    <div in:scale out:fade={{duration: 200}}>
        <FeedbackItem item={fb} />
    </div>
{/each}