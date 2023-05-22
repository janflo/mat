<script>
	import MaterialApp from "svelte-materialify/src/components/MaterialApp/MaterialApp.svelte";
	import Button from "svelte-materialify/src/components/Button/Button.svelte";
	import { Card, CardText, CardActions } from 'svelte-materialify';
	import { ExpansionPanel, ExpansionPanels, AppBar, Divider } from "svelte-materialify";
	import { Menu, List, ListItem, Container, Row, Col, Footer, Icon } from 'svelte-materialify';
	import {  mdiMenu, mdiDotsVertical } from '@mdi/js'; 
	let theme = 'light';
	const links = ['Home', 'About', 'Team', 'Services', 'Contact Us'];
	function toggleTheme() {
		if (theme === 'light') theme = 'dark';
		else theme = 'light';
	}
	let fluid = false;
	let value = [0];
  let about = { index: '', active: '' };
  function onChange(e) {
    about = e.detail;
  }
</script>

<MaterialApp {theme}>
	<Container {fluid}  >
	<AppBar>
		<div slot="icon">
			<Button fab depressed>
			  <Icon path={mdiMenu} />
			</Button>
		  </div>
		<span slot="title">Bilt</span>
		<div style="flex-grow:1" />
		<Button on:click={toggleTheme} >Toggle Theme</Button>
		<Menu right>
			<div slot="activator">
			  <Button fab depressed>
				<Icon path={mdiDotsVertical} />
			  </Button>
			</div>
			<List>
				<ListItem>Option 1</ListItem>
				<ListItem>Option 2</ListItem>
				<ListItem>This is Cool</ListItem>
			  </List>
		  </Menu>
	</AppBar>
	<br />
	<h2 class="mb-4 text-center">
		Svelte Materialify
	</h2>
	<Divider />
	<br>
	<div class="text-center">
		<a href="//github.com/TheComputerM/svelte-materialify/stargazers">
			<Button class="primary-color">
				Star on GitHub
			</Button>
		</a>
		<Button on:click={toggleTheme}>Toggle Theme</Button>
	</div>
	<br />
	<div class="d-flex justify-center mt-4 mb-4 ">
		<Card outlined  class=" elevation-10" style="max-width:300px;">
		  <div class="pl-4 pr-4 pt-3">
			<span class="text-overline"> OVERLINE </span>
			<br />
			<span class="text-h5 mb-2">Headline</span>
			<br />
		  </div>
		  <CardText>
			Lorem ipsum dolor sit amet consectetur adipisicing elit. Reprehenderit, qui quaerat
			rerum incidunt nisi ducimus?
		  </CardText>
		  <CardActions>
			<Button rounded outlined>Button</Button>
		  </CardActions>
		</Card>
	  </div>

	  <ExpansionPanels on:change={onChange} bind:value>
		<ExpansionPanel>
		  <span slot="header">Item</span>
		  Lorem ipsum dolor sit amet consectetur, adipisicing elit. Repellat amet natus obcaecati
		  molestiae quas mollitia error modi atque aliquam esse.
		</ExpansionPanel>
		<ExpansionPanel>
		  <span slot="header">Item</span>
		  Lorem ipsum dolor sit amet consectetur, adipisicing elit. Repellat amet natus obcaecati
		  molestiae quas mollitia error modi atque aliquam esse.
		</ExpansionPanel>
		<ExpansionPanel >
		  <span slot="header">Był Disabled</span>
		  Lorem ipsum dolor sit amet consectetur, adipisicing elit. Repellat amet natus obcaecati
		  molestiae quas mollitia error modi atque aliquam esse.
		</ExpansionPanel>
		<ExpansionPanel>
		  <span slot="header">Item</span>
		  Lorem ipsum dolor sit amet consectetur, adipisicing elit. Repellat amet natus obcaecati
		  molestiae quas mollitia error modi atque aliquam esse.
		</ExpansionPanel>
	  </ExpansionPanels>

	  <Footer padless class="indigo theme--dark justify-center flex-column">
		<div class="mt-2 mb-2">
		  {#each links as link}
			<Button text rounded>{link}</Button>
		  {/each}
		</div>
		<div class="indigo lighten-1 pa-2 text-center" style="width:100%">
		  2020 -
		  <b>Svelte Materialify</b>
		</div>
	  </Footer>
	</Container>
</MaterialApp>

<style>
	
</style>