<script>
	import { page } from '$app/stores';

	$: path = $page.url.pathname;
	let tabs = [
		{ name: '디자인', path: '/Design' },
		{ name: '글자', path: '/Text' },
		{ name: '색상/마감', path: '/FnPaint' },
		{ name: 'LED', path: '/LED' },
        { name: '홀더', path: '/Holder' }
	];
</script>

<div class="flex flex-col h-full">
	<nav class="flex md:flex-row justify-between md:justify-start md:space-x-0 space-x-2 text-[#000000]">
		{#each tabs as tab, i (i)}
			<a
				href={tab.path}
				class={`${ path === tab.path ? 'bg-teal-300	border-amber-50	 border-2 shadow-cyan-500 shadow-md' : 'bg-teal-50' } p-2 w-1/5  shadow-md shadow-zinc-700/30 text-center`}
			>
				{tab.name}
			</a>
		{/each}
	</nav>
</div>

