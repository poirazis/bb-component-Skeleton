<script lang="ts">
  import { getContext } from "svelte";

  interface SDKContext {
    styleable: (node: HTMLElement, styles: any) => void;
  }

  interface ComponentContext {
    styles: any;
  }

  const sdk = getContext<SDKContext>("sdk");
  const componentContext = getContext<ComponentContext>("component");

  const { styleable } = sdk;

  let count: number = $state(0);
  let { buttonLabel }: { buttonLabel?: string } = $props();
</script>

<div use:styleable={componentContext.styles}>
  <button onclick={() => count++}>
    {buttonLabel || "Click me"} ({count})
  </button>
</div>

<style>
  div {
    padding: 1rem;
    border: 1px solid #ccc;
    display: inline-block;
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
