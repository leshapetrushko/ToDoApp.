<script>
    export let id = 0;
    export let text = "Text";
    export let status = false;
    import { createEventDispatcher } from 'svelte';
    const dispatch = createEventDispatcher();
    function onChange() {
        dispatch('change', {id})
    }

    function onRemove() {
        dispatch('remove', { id });
    }
</script>

<div class="todo-item" class:todo-item_done={status}>
    <input type="checkbox" checked={status} on:change={onChange} />
    <span> {text} </span>
    <button class="todo-item_btn" on:click={onRemove}>Удалить</button>
</div>

<style>
    .todo-item {
        background: #ffebeb;
        padding: 20px;
        border-radius: 10px;
        display: grid;
        grid-template-columns: auto 1fr auto;
        gap: 30px;
        align-items: center;
    }
    .todo-item_btn {
        background: red;
        border-radius: 5px;
        border: none;
        padding: 10px;
        color: white;
    }
    .todo-item_done {
        background: #ebffed;
    }
</style>