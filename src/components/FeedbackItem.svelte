<script lang="ts">
    // Core
    // import { createEventDispatcher } from 'svelte';

    // Components
    import Card from './Card.svelte';

    // Store
    import { FeedbackStore } from '../store';

    interface Props {
        id: number,
        rating: number,
        text: string
    }
    export let item: Props;

    // const dispatch = createEventDispatcher();
    const handleDelete = (id:number) => {
        // dispatch('delete-feedback', id)
        FeedbackStore.update((currentFeedback) => {
            return currentFeedback.filter(o => o.id !== id);
        });
    };
</script>

<Card>
    <div class="num-display">
        { item.rating }
    </div>
    <button class="close" on:click={ () => handleDelete(item.id) }>X</button>
    <p class="text-display">
        { item.text }
    </p>
</Card>

<style>
    .num-display {
        position: absolute;
        top: -10px;
        left: -10px;
        width: 50px;
        height: 50px;
        background: #ff6a95;
        color: #fff;
        border: 1px #eee solid;
        border-radius: 50%;
        padding: 10px;
        text-align: center;
        font-size: 19px;
    }

    .close {
        position: absolute;
        top: 10px;
        right: 20px;
        cursor: pointer;
        background: none;
        border: none;
    }
</style>