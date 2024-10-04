<script>
  export let isOn = false;  // Allow external control of the toggle state
  export let isDisabled = false; // Control whether the toggle is interactive
  export let darkMode = false;  // Add a dark mode prop to control the appearance
</script>

<div class="space-y-4">
  <div class="flex items-center space-x-4">
    <label for="primarySwitch" class="text-sm font-medium"></label>
    <div
      class="relative inline-flex items-center cursor-pointer w-10 h-6"
      role="switch"
      aria-checked={isOn}
      tabindex="0"
      class:cursor-not-allowed={isDisabled}
      on:click={!isDisabled ? () => isOn = !isOn : null}
      on:keydown={!isDisabled ? (e) => e.key === 'Enter' && (isOn = !isOn) : null}
    >
      <input id="primarySwitch" type="checkbox" class="sr-only" bind:checked={isOn} />
      <div class={`w-full h-full rounded-full transition-colors duration-200 ${darkMode ? 'bg-gray-700' : 'bg-gray-300'} hover:${darkMode ? 'bg-gray-800' : 'bg-gray-400'}`}></div>
      <div
        class="absolute w-4 h-4 bg-purple-600 rounded-full transform transition-transform duration-200"
        style="left: 0.25rem; top: 0.25rem;"
        class:translate-x-3={isOn}
      ></div>
    </div>
  </div>
</div>

<style>
  .translate-x-3 {
    transform: translateX(1rem); /* Moves to the right */
  }

  .cursor-pointer {
    outline: none;
    border: none;
  }

  .cursor-not-allowed {
    pointer-events: none;
  }
</style>
