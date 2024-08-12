<script>
  import { Tabs, TabItem, Button, Helper } from 'flowbite-svelte';

  $: tabItems = [
    {
      id: 1,
      title: 'Tab 1',
      content: 'Tab 1 Content'
    },
    {
      id: 2,
      title: 'Tab 2',
      content: 'Tab 2 Content'
    },
    {
      id: 3,
      title: 'Tab 3',
      content: 'Tab 3 Content'
    },
    {
      id: 4,
      title: 'Tab 4',
      content: 'Tab 4 Content'
    },
    {
      id: 5,
      title: 'Tab 5',
      content: 'Tab 5 Content'
    },
    {
      id: 6,
      title: 'Tab 6',
      content: 'Tab 6 Content'
    },
  ];

  function handleRemoveTab(index) {
    tabItems = tabItems.filter((_, i) => i !== index);
  }
</script>

<Helper class="mb-4">Please wait until Delete button is showed and Try to delete last tab to see the bug</Helper>

<Tabs>
  {#each tabItems as tab, idx}
    <TabItem open={idx === 0} title={tab.title}>
      <Button class="mb-2" on:click={() => handleRemoveTab(idx)}>Click me to delete tab {tab.id}</Button>
      <p class="text-sm text-gray-500 dark:text-gray-400">
        {tab.content}
      </p>
    </TabItem>
  {/each}
</Tabs>