<script lang="ts">
    import FeedbackItem from './FeedbackItem.svelte';

    interface Props {
        id: number,
        rating: number,
        text: string
    }
    export let feedback: Props[] = [];
</script>

{#each feedback as fb (fb.id)}
    <FeedbackItem item={fb} on:delete-feedback />
{/each}
