<script>
	import { goto } from '$app/navigation';
	import { kodamStore, namaStore } from '$lib/store';

	const khodam = [
		'buaya tello',
		'bereng bereng',
		'mall sudiang',
		'kampas rem',
		'mamat ',
		'pitti',
		'yanti gotong'
	];

	import Icon from '@iconify/svelte';
	import { RingLoader } from 'svelte-loading-spinners';

	let loading = false;
	let nama = '';

	function onSubmit() {
		loading = true;

		namaStore.set(nama);

		var item = khodam[Math.floor(Math.random() * khodam.length)];

		kodamStore.set(item);

		setTimeout(() => {
			loading = false;
			goto('/khodam');
		}, 3000);
	}
</script>

<div class="rounded-xl bg-slate-800 p-5 shadow">
	{#if !loading}
		<form on:submit={onSubmit}>
			<label for="nama">Masukkan nama Anda :</label>
			<input
				type="text"
				class="rounded-2xl w-full mt-3 bg-transparent px-4 py-3 border border-slate-200 focus:outline focus:outline-slate-200 focus:outline-offset-4 outline-none"
				id="nama"
				name="nama"
				bind:value={nama}
				placeholder="Nyolit"
				required
			/>

			<button
				class="w-full mt-4 py-4 rounded-2xl text-white flex justify-center gap-2 items-center font-semibold text-lg bg-slate-900 border hover:bg-transparent hover:text-slate-900 border-slate-900 ease-in-out duration-300 transition-all"
			>
				Cek Kodam
				<Icon icon="icon-park-twotone:search" width="1.2em" height="1.2em" />
			</button>
		</form>
	{/if}

	{#if loading}
		<div class="w-96 flex justify-center items-center flex-col gap-3">
			<h1 class=" font-bold text-lg">Memeriksa khodam Anda</h1>
			<RingLoader color="#0F172A" />
			<h1 class=" font-bold text-lg">Mohon menunggu sesaat</h1>
		</div>
	{/if}
</div>
