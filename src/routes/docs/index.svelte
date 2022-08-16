<script context="module">
	import Card from './Card.svelte';
	import ArrayUpdate from './ArrayUpdate.svelte';
	const imgUrl = 'https://t7.baidu.com/it/u=2131121619,3431382222&fm=193&f=GIF';
</script>

<svelte:head>
	<title>Docs</title>
	<meta name="description" content="Docs this app" />
</svelte:head>

<div class="content">
	<li>图片资源使用</li>
	<img src={imgUrl} alt="" width="150" />
	<li>组件使用</li>
	<Card />
	<ArrayUpdate target="hello" />
</div>

<style>
	.content {
		width: 100%;
		max-width: var(--column-width);
		margin: var(--column-margin-top) auto 0 auto;
	}
</style>
