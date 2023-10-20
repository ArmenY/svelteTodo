<script>
    export let showModal;
</script>
{#if showModal}
    <div class="todoForm--backDrop" on:click|self>
        <slot></slot>
    </div>
{/if}
<style>
    .todoForm--backDrop {
        position: fixed;
        width: 100%;
        height: 100%;
        background: #000000cc;
    }
</style>