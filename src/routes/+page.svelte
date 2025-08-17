<script lang="ts">
	import ThreeScene from '$lib/components/ThreeScene.svelte';
</script>

<!-- Hero Section -->
<section class="relative min-h-screen flex items-center justify-center overflow-hidden">
	<div class="absolute inset-0 z-0">
		<ThreeScene sceneType="hero" />
	</div>
	
	<div class="relative z-10 text-center px-6 max-w-4xl mx-auto">
		<h1 class="text-6xl md:text-8xl font-bold mb-6 glow-text text-yellow-400">
			สู่สุคติ
		</h1>
		<p class="text-xl md:text-2xl mb-8 text-gray-300 leading-relaxed">
			เอาชีวิตรอดกลางวัน ทำพิธีส่งวิญญาณกลางคืน<br>
			ในโลกไทยร่วมสมัยที่เต็มไปด้วยผีไทยหลากชนิด
		</p>
		<div class="flex flex-col sm:flex-row gap-4 justify-center">
			<button class="bg-gradient-to-r from-yellow-600 to-orange-600 hover:from-yellow-500 hover:to-orange-500 px-8 py-4 rounded-lg font-semibold text-lg transition-all transform hover:scale-105">
				เกมเต็มเร็ว ๆ นี้
			</button>
			<button class="border-2 border-yellow-600 text-yellow-400 hover:bg-yellow-600 hover:text-black px-8 py-4 rounded-lg font-semibold text-lg transition-all">
				ดูตัวอย่างได้เร็ว ๆ นี้
			</button>
		</div>
	</div>
</section>

<!-- Game Overview Section -->
<section id="overview" class="py-20 px-6">
	<div class="container mx-auto max-w-6xl">
		<h2 class="text-4xl md:text-5xl font-bold text-center mb-12 text-yellow-400 glow-text">
			แกนเกม (Core Fantasy)
		</h2>
		
		<div class="grid md:grid-cols-2 gap-12 items-center">
			<div class="space-y-6">
				<div class="ghost-blur rounded-lg p-6 border border-yellow-600/30">
					<h3 class="text-2xl font-semibold mb-4 text-orange-400">🌅 กลางวัน: เอาชีวิตรอด</h3>
					<ul class="space-y-2 text-gray-300">
						<li>• หางานทำเพื่อหาเงิน</li>
						<li>• ซื้ออาหารกันหิว</li>
						<li>• ใส่บาตรและทำบุญเพื่อสะสมแต้มบุญ</li>
						<li>• เตรียมเครื่องพิธีสำหรับกลางคืน</li>
					</ul>
				</div>
				
				<div class="ghost-blur rounded-lg p-6 border border-yellow-600/30">
					<h3 class="text-2xl font-semibold mb-4 text-purple-400">🌙 กลางคืน: ทำพิธีส่งวิญญาณ</h3>
					<ul class="space-y-2 text-gray-300">
						<li>• อยู่ในวัดเป็นฐานปลอดภัย</li>
						<li>• ใช้แต้มบุญออกนอกวัดอย่างปลอดภัย</li>
						<li>• เผชิญหน้าผีตัวเป้าหมาย</li>
						<li>• ทำพิธีส่งวิญญาณไปสุคติ</li>
					</ul>
				</div>
			</div>
			
			<div class="relative h-96">
				<ThreeScene sceneType="spirits" />
			</div>
		</div>
	</div>
</section>

<!-- Thai Spirits Section -->
<section id="spirits" class="py-20 px-6 bg-black/20">
	<div class="container mx-auto max-w-6xl">
		<h2 class="text-4xl md:text-5xl font-bold text-center mb-12 text-yellow-400 glow-text">
			ผีไทยหลากชนิด
		</h2>
		
		<div class="grid md:grid-cols-3 gap-8">
			<div class="ghost-blur rounded-lg p-6 border border-red-600/30 text-center">
				<div class="text-6xl mb-4">👻</div>
				<h3 class="text-2xl font-semibold mb-4 text-red-400">กระสือ</h3>
				<p class="text-gray-300 mb-4">วิญญาณหัวลอยกินของสกปรก กลัวแสงไฟและมีดปลาบปลื้ง</p>
				<div class="bg-red-900/20 rounded p-3">
					<span class="text-sm text-red-300">จุดอ่อน: แสงไฟสว่าง, ใบมีดที่คม</span>
				</div>
			</div>
			
			<div class="ghost-blur rounded-lg p-6 border border-green-600/30 text-center">
				<div class="text-6xl mb-4">🧌</div>
				<h3 class="text-2xl font-semibold mb-4 text-green-400">ปอบ</h3>
				<p class="text-gray-300 mb-4">ผีเสื้อในตัวคน กินอาหารดิบและมีพฤติกรรมแปลก</p>
				<div class="bg-green-900/20 rounded p-3">
					<span class="text-sm text-green-300">จุดอ่อน: พิธีไล่ปอบด้วยเครื่องแกง</span>
				</div>
			</div>
			
			<div class="ghost-blur rounded-lg p-6 border border-blue-600/30 text-center">
				<div class="text-6xl mb-4">💀</div>
				<h3 class="text-2xl font-semibold mb-4 text-blue-400">เปรต</h3>
				<p class="text-gray-300 mb-4">วิญญาณที่หิวโหยตลอดกาล มองหาอาหารและน้ำ</p>
				<div class="bg-blue-900/20 rounded p-3">
					<span class="text-sm text-blue-300">จุดอ่อน: การทำบุญถวายอาหาร</span>
				</div>
			</div>
		</div>
	</div>
</section>

<!-- Ritual System Section -->
<section id="rituals" class="py-20 px-6">
	<div class="container mx-auto max-w-6xl">
		<h2 class="text-4xl md:text-5xl font-bold text-center mb-12 text-yellow-400 glow-text">
			ระบบพิธีกรรม
		</h2>
		
		<div class="grid md:grid-cols-2 gap-12 items-center">
			<div class="relative h-96">
				<ThreeScene sceneType="ritual" />
			</div>
			
			<div class="space-y-6">
				<div class="ghost-blur rounded-lg p-6 border border-yellow-600/30">
					<h3 class="text-2xl font-semibold mb-4 text-yellow-400">เครื่องพิธี</h3>
					<ul class="space-y-2 text-gray-300">
						<li>🕯️ เทียน - ไล่ความมืด</li>
						<li>🌸 ดอกไม้ - บูชาเทพารักษ์</li>
						<li>🧿 ของศักดิ์สิทธิ์ - คุ้มครองจากผี</li>
						<li>📿 ยันต์ - เสริมพลังในพิธี</li>
					</ul>
				</div>
				
				<div class="ghost-blur rounded-lg p-6 border border-yellow-600/30">
					<h3 class="text-2xl font-semibold mb-4 text-orange-400">การทำพิธี</h3>
					<p class="text-gray-300">
						แต่ละผีต้องใช้พิธีกรรมเฉพาะ มินิเกมแบบจังหวะเวลา 
						การวางของพิธี และการสวดคาถาแบบโต้ตอบ
					</p>
				</div>
			</div>
		</div>
	</div>
</section>

<!-- Features Section -->
<section id="features" class="py-20 px-6 bg-black/20">
	<div class="container mx-auto max-w-6xl">
		<h2 class="text-4xl md:text-5xl font-bold text-center mb-12 text-yellow-400 glow-text">
			ฟีเจอร์เด่น
		</h2>
		
		<div class="grid md:grid-cols-2 lg:grid-cols-3 gap-8">
			<div class="ghost-blur rounded-lg p-6 border border-purple-600/30 text-center">
				<div class="text-4xl mb-4">⚖️</div>
				<h3 class="text-xl font-semibold mb-3 text-purple-400">ระบบแต้มบุญ</h3>
				<p class="text-gray-300 text-sm">ใช้บุญเป็นทรัพยากรหลักในการคุ้มครองและทำพิธี</p>
			</div>
			
			<div class="ghost-blur rounded-lg p-6 border border-orange-600/30 text-center">
				<div class="text-4xl mb-4">🏛️</div>
				<h3 class="text-xl font-semibold mb-3 text-orange-400">โลกไทยร่วมสมัย</h3>
				<p class="text-gray-300 text-sm">สำรวจเมืองไทยจากตลาด ชุมชน ไปจนถึงวัดเก่า</p>
			</div>
			
			<div class="ghost-blur rounded-lg p-6 border border-green-600/30 text-center">
				<div class="text-4xl mb-4">📖</div>
				<h3 class="text-xl font-semibold mb-3 text-green-400">เนื้อเรื่องลึกซึ้ง</h3>
				<p class="text-gray-300 text-sm">ค้นหาความจริงเบื้องหลังอุบัติเหตุก่อสร้าง</p>
			</div>
			
			<div class="ghost-blur rounded-lg p-6 border border-red-600/30 text-center">
				<div class="text-4xl mb-4">🎭</div>
				<h3 class="text-xl font-semibold mb-3 text-red-400">วัฒนธรรมไทย</h3>
				<p class="text-gray-300 text-sm">ผสมผสานความเชื่อและตำนานไทยอย่างลึกซึ้ง</p>
			</div>
			
			<div class="ghost-blur rounded-lg p-6 border border-blue-600/30 text-center">
				<div class="text-4xl mb-4">🎮</div>
				<h3 class="text-xl font-semibold mb-3 text-blue-400">เกมเพลย์หลากหลาย</h3>
				<p class="text-gray-300 text-sm">ผสมผสานการเอาชีวิตรอด จัดการทรัพยากร และพัซเซิล</p>
			</div>
			
			<div class="ghost-blur rounded-lg p-6 border border-yellow-600/30 text-center">
				<div class="text-4xl mb-4">🔄</div>
				<h3 class="text-xl font-semibold mb-3 text-yellow-400">ลูปเกมน่าเล่น</h3>
				<p class="text-gray-300 text-sm">วงจรกลางวันกลางคืนที่ท้าทายและติดเสพ</p>
			</div>
		</div>
	</div>
</section>

<!-- Call to Action -->
<section class="py-20 px-6 text-center">
	<div class="container mx-auto max-w-4xl">
		<h2 class="text-4xl md:text-5xl font-bold mb-6 text-yellow-400 glow-text">
			พร้อมเริ่มต้นภารกิจแล้วหรือยัง?
		</h2>
		<p class="text-xl mb-8 text-gray-300">
			ช่วยส่งลูกน้องทุกดวงวิญญาณไปสู่สุคติ และค้นหาความจริงเบื้องหลังโศกนาฏกรรม
		</p>
		<div class="flex flex-col sm:flex-row gap-4 justify-center">
			<!-- <button class="bg-gradient-to-r from-yellow-600 to-orange-600 hover:from-yellow-500 hover:to-orange-500 px-12 py-4 rounded-lg font-bold text-xl transition-all transform hover:scale-105">
				ดาวน์โหลดเกม
			</button> -->
			<button class="border-2 border-yellow-600 text-yellow-400 hover:bg-yellow-600 hover:text-black px-12 py-4 rounded-lg font-bold text-xl transition-all">
				อ่านรายละเอียดเพิ่มเติม (เร็ว ๆ นี้)
			</button>
		</div>
	</div>
</section>
