<div style="min-width: 100px;">
  <Button on:click={() => menu.setOpen(true)}>
    <Label>Open Menu</Label>
  </Button>
  <Menu bind:this={menu}>
    <List>
      <Item on:SMUI:action={() => (clicked = 'Cut')}>
        <a href="/sveltematerialui/Accordion">Accordion</a>
      </Item>
      <Item on:SMUI:action={() => (clicked = 'Copy')}>
        <Text>Copy</Text>
      </Item>
      <Item on:SMUI:action={() => (clicked = 'Paste')}>
        <Text>Paste</Text>
      </Item>
      <Separator />
      <Item on:SMUI:action={() => (clicked = 'Delete')}>
        <Text>Delete</Text>
      </Item>
    </List>
  </Menu>
</div>


<script lang="ts">
  import Menu from '@smui/menu';
  import List, { Item, Separator, Text } from '@smui/list';
  import Button, { Label } from '@smui/button';
	import { onMount } from 'svelte';

  let menu: Menu;

	onMount(() => {
			menu.setOpen(true)
	});
  let clicked = 'nothing yet';
</script>
