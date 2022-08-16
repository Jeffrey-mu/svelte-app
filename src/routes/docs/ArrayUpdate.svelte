<script lang="ts">
	// 组件传值
	export let target: string;
	let numbers: number[] = [0];
	const foo = {
		bar: 'bar'
	};
	function pushArray() {
		// numbers.push(numbers.length);
		// push 不会触发视图更新 需要重新赋值
		// numbers = numbers;
		// 更加简洁
		numbers = [...numbers, numbers.length + 1];
	}
	function setFooBat() {
		foo.bar = 'baz';
	}
	const cats = [
		{
			name: 'zs',
			id: 1
		},
		{
			name: 'jack',
			id: 2
		}
	];
	function promise() {
		return new Promise((resolve, reject) => {
			setTimeout(() => resolve('hello'), 2000);
		});
	}
</script>

<div class="card">
	<!-- 条件渲染 -->
	{#if true}
		<h1>{target}</h1>
	{:else}
		<h1>defualt</h1>
	{/if}
	<!-- 支持if else if else -->
	pushArray 对数组进行push、 push 不会触发视图更新 需要重新赋值
	<h2>numbers 最后一个元素:{numbers.at(-1)}</h2>
	<button on:click={pushArray}> pushItem </button>

	<h2>foo.bar:{foo.bar}</h2>
	<button on:click={setFooBat}> setFooBat </button>
	<!-- 使用each遍历 -->
	<ul>
		<!-- 解构操作 -->
		<!-- {#each cats as {id, name}, index} -->
		<!-- (cat.id) 标识更新是的id -->
		{#each cats as cat, index (cat.id)}
			<li>
				{index + 1}:
				<a target="_blank" href="https://www.youtube.com/watch?v={cat.id}">
					{cat.name}
				</a>
			</li>
		{/each}
	</ul>
	{#await promise()}
		<p>...waiting</p>
	{:then number}
		<p>The number is {number}</p>
	{:catch error}
		<p style="color: red">{error.message}</p>
	{/await}
	<!-- on: 绑定可以绑定任何事件 支持声明事件-->
	<!-- <button type="button" on:click={func}></button>-->
	<!-- 支持修饰符如 once -->
	<!-- 支持修饰符如 once | preventDefault | stopPropagation | passive | nonpassive | self | trusted-->
	<!-- 支持on:click|once|capture={...} -->
	<button on:click|once={() => alert(1)}> Click me </button>
</div>
