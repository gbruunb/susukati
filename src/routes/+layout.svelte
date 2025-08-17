<script lang="ts">
	import '../app.css';
	import favicon from '$lib/assets/favicon.svg';
	
	let { children } = $props();
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
	<title>สู่สุคติ</title>
	<meta name="description" content="เกมเอาชีวิตรอดกลางวัน ทำพิธีส่งวิญญาณกลางคืน ในโลกที่เต็มไปด้วยผีไทยหลากชนิด" />
</svelte:head>

<div class="min-h-screen thai-pattern">
	<nav class="fixed top-0 w-full z-50 ghost-blur border-b border-yellow-600/30">
		<div class="container mx-auto px-6 py-4">
			<div class="flex items-center justify-between">
				<h1 class="text-2xl font-bold text-yellow-400 glow-text">สู่สุคติ</h1>
				<div class="hidden md:flex space-x-6">
					<a href="#overview" class="text-gray-300 hover:text-yellow-400 transition-colors">เกมเพลย์</a>
					<a href="#spirits" class="text-gray-300 hover:text-yellow-400 transition-colors">ผีไทย</a>
					<a href="#rituals" class="text-gray-300 hover:text-yellow-400 transition-colors">พิธีกรรม</a>
					<a href="#features" class="text-gray-300 hover:text-yellow-400 transition-colors">ฟีเจอร์</a>
				</div>
				
				<!-- Mobile menu button -->
				<button class="md:hidden text-gray-300 hover:text-yellow-400" 
						aria-label="เปิดเมนู"
						onclick={() => {
							const menu = document.getElementById('mobile-menu');
							if (menu) menu.classList.toggle('hidden');
						}}>
					<svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
						<path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16"></path>
					</svg>
				</button>
			</div>
		</div>
		
		<!-- Mobile menu -->
		<div id="mobile-menu" class="hidden md:hidden ghost-blur border-t border-yellow-600/30">
			<div class="container mx-auto px-6 py-4">
				<div class="flex flex-col space-y-4">
					<a href="#overview" class="text-gray-300 hover:text-yellow-400 transition-colors">เกมเพลย์</a>
					<a href="#spirits" class="text-gray-300 hover:text-yellow-400 transition-colors">ผีไทย</a>
					<a href="#rituals" class="text-gray-300 hover:text-yellow-400 transition-colors">พิธีกรรม</a>
					<a href="#features" class="text-gray-300 hover:text-yellow-400 transition-colors">ฟีเจอร์</a>
				</div>
			</div>
		</div>
	</nav>

	<main class="pt-20">
		{@render children?.()}
	</main>

	<footer class="border-t border-yellow-600/30 ghost-blur mt-20">
		<div class="container mx-auto px-6 py-8">
			<div class="text-center text-gray-400">
				<p>© 2025 สู่สุคติ</p>
				<p class="text-sm mt-2">เกมแนวเอาชีวิตรอดผสมผสานวัฒนธรรมไทย</p>
				<p class="text-sm mt-1 text-yellow-400">จัดทำโดย ทีมหนึ่งคืนสยอง</p>
			</div>
		</div>
	</footer>
</div>
