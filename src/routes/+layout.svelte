<script>
	import '$lib/tailwind.css';
	import Icon from '@iconify/svelte';
</script>

<div
	class="w-full h-screen bg-slate-900 gap-5 flex-col px-10 text-white flex justify-center items-center"
>
	<div class="w-full flex items-center justify-center gap-3">
		<Icon icon="la:ghost" width="1.9rem" height="1.9rem" />
		<h1 class="font-bold text-3xl">Khodam Saya</h1>
		<Icon icon="la:ghost" width="1.9rem" height="1.9rem" />
	</div>

	<slot />
</div>
