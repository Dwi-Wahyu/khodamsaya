<script>
	import { kodamStore, namaStore } from '$lib/store';
	import Icon from '@iconify/svelte';

	$: nama = $namaStore;
	$: kodam = $kodamStore;
</script>

<div class="rounded-xl bg-slate-800 p-5 shadow">
	<h1 class="text-lg">
		Khodam
		<span
			class="bg-gray-100 text-gray-800 font-medium px-2.5 py-0.5 mx-1 rounded dark:bg-gray-700 dark:text-gray-400 border border-gray-500"
		>
			{nama}
		</span>
		adalah
	</h1>
	<div class="flex items-center mt-4 mb-2 justify-center gap-2">
		<Icon icon="rivet-icons:lightning" width="1.2em" height="1.2em" />
		<h1 class="text-2xl font-bold">
			{kodam}
		</h1>
		<Icon icon="rivet-icons:lightning" width="1.2em" height="1.2em" />
	</div>
</div>

<a href="/" class="underline underline-offset-4">Coba Nama Lain</a>
