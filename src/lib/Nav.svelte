<script>
	import { page } from '$app/stores';

	$: path = $page.url.pathname;
	let tabs = [
		{ name: '디자인', path: '/Design', active:'true'},
		{ name: '글자', path: '/Text' , active:'false'},
		{ name: '색&마감', path: '/FnPaint' , active:'false'},
		{ name: 'LED', path: '/LED' , active:'false'},
        { name: '홀더', path: '/Holder' , active:'false'}
	];
</script>

<div class="flex flex-col h-full">
	<nav class="flex md:flex-row justify-between md:justify-start md:space-x-0 text-[#000000]">
		{#each tabs as tab, i (i)}
			<a
				href={tab.path}
				class={`${ path === tab.path ? 'bg-teal-300	border-amber-50	 shadow-cyan-500 shadow-md' : 'bg-teal-50' } p-2 w-1/5   text-center`}
			>
				{tab.name}
			</a>
		{/each}
	</nav>
</div>

