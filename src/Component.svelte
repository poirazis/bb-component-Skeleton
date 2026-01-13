<script lang="ts">
  import { getContext } from "svelte";

  const { styleable } = getContext("sdk");
  const component = getContext("component");

  let count: number = $state(0);
  let { buttonLabel }: { buttonLabel?: string } = $props();
</script>

<div class="super-wrapper" use:styleable={$component.styles}>
  <button onclick={() => count++}>
    {buttonLabel || "Click me"} ({count})
  </button>
</div>

<style>
  .super-wrapper {
    display: flex;
    align-items: center;
    justify-content: center;
  }
  button {
    padding: 0.75rem 1.5rem;
    background-color: #007bff;
    color: white;
    border: none;
    border-radius: 4px;
    cursor: pointer;
    font-size: 1rem;
    font-weight: 600;
    transition: background-color 0.2s ease;
  }

  button:hover {
    background-color: #0056b3;
  }

  button:active {
    background-color: #004085;
  }
</style>
