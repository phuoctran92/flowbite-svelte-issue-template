<script>
  import { Tabs, TabItem, Button } from 'flowbite-svelte';

  let tabItems = [
    {
      id: crypto.randomUUID(),
      title: 'Tab 1',
      content: 'Tab 1 Content'
    },
    {
      id: crypto.randomUUID(),
      title: 'Tab 2',
      content: 'Tab 2 Content'
    },
    {
      id: crypto.randomUUID(),
      title: 'Tab 3',
      content: 'Tab 3 Content'
    },
    {
      id: crypto.randomUUID(),
      title: 'Tab 4',
      content: 'Tab 4 Content'
    },
    {
      id: crypto.randomUUID(),
      title: 'Tab 5',
      content: 'Tab 5 Content'
    },
    {
      id: crypto.randomUUID(),
      title: 'Tab 6',
      content: 'Tab 6 Content'
    },
  ];

  function removeLastTab() {
    if (tabItems.length > 0) {
      tabItems = tabItems.slice(0, -1);
    }
  }

  function handleRemoveTab(index) {
    tabItems = tabItems.filter((_, i) => i !== index);
  }
</script>

<Tabs>
  {#each tabItems as tab, idx}
    <TabItem open={idx === 0} title={tab.title}>
      <Button on:click={() => handleRemoveTab(idx)}>Delete</Button>
      <p class="text-sm text-gray-500 dark:text-gray-400">
        {tab.content}
      </p>
    </TabItem>
  {/each}
</Tabs>

<pre>
{JSON.stringify(tabItems)}
</pre>