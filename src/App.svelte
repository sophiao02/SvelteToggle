<svelte:head>
  <link rel="stylesheet" href="https://unpkg.com/tailwindcss@2.2.19/dist/tailwind.min.css" />
</svelte:head>

<script>
  import Toggle from './components/Toggle.svelte'; // Import the Toggle component
  let isDisabled = true; // State for the disabled version of the toggle
</script>

<main class="p-4">
  <h1 class="text-2xl font-bold mb-4">Svelte Toggle Component</h1>

  <!-- Primary Toggle -->
  <h2 class="text-sm font-medium mb-2">Primary</h2>
  <Toggle />

  <!-- Secondary (Dark Mode) Toggle -->
  <h2 class="text-sm font-medium mt-4">Secondary</h2>
  <Toggle darkMode={true} />  <!-- Pass darkMode as true -->

  <!-- Disabled Toggle -->
  <h2 class="text-sm font-medium mt-4">Disabled</h2>
  <div class="opacity-50 cursor-not-allowed">
    <Toggle isOn={isDisabled} isDisabled={true} />
  </div>
</main>

<style>
  main {
    padding: 2rem;
    font-family: Arial, sans-serif;
  }
</style>
