<script>
    import { createEventDispatcher } from 'svelte';
    const dispatch = createEventDispatcher();
    
    let inputValue = '';

    function onAdd() {
        if(inputValue.length) {
            dispatch('add', { text: inputValue });
        }
        inputValue = '';
    }
</script>

<div class="todo_controls">
    <input class="todo_controls-input" type="text" bind:value={inputValue} />
    <button class="todo_controls-btn" on:click={onAdd}>Добавить</button>
    <div>{inputValue}</div> 
</div>

<style>
    .todo_controls {
        display: grid;
        grid-template-columns: 70% 30%;
    }
    .todo_controls-input {
        border: none;
        padding: 20px 10px;
        border-radius: 10px 0 0 10px;
    }
    .todo_controls-btn {
        border: none;
        padding: 10px;
        border-radius: 0 10px 10px 0;
        background: #fbcc28;
    }
</style>