<script lang="ts">
	import { onMount } from 'svelte';
	import * as THREE from 'three';

	export let sceneType: 'hero' | 'spirits' | 'ritual' = 'hero';
	
	let canvas: HTMLCanvasElement;
	let scene: THREE.Scene;
	let camera: THREE.PerspectiveCamera;
	let renderer: THREE.WebGLRenderer;
	let animationFrame: number;

	onMount(() => {
		initThreeJS();
		createScene();
		animate();

		return () => {
			if (animationFrame) {
				cancelAnimationFrame(animationFrame);
			}
			if (renderer) {
				renderer.dispose();
			}
		};
	});

	function initThreeJS() {
		scene = new THREE.Scene();
		camera = new THREE.PerspectiveCamera(75, canvas.clientWidth / canvas.clientHeight, 0.1, 1000);
		renderer = new THREE.WebGLRenderer({ canvas, alpha: true, antialias: true });
		renderer.setSize(canvas.clientWidth, canvas.clientHeight);
		renderer.setClearColor(0x000000, 0);
	}

	function createScene() {
		if (sceneType === 'hero') {
			createHeroScene();
		} else if (sceneType === 'spirits') {
			createSpiritsScene();
		} else if (sceneType === 'ritual') {
			createRitualScene();
		}
	}

	function createHeroScene() {
		// Floating orbs representing spirits
		const orbGeometry = new THREE.SphereGeometry(0.1, 16, 16);
		const orbMaterial = new THREE.MeshBasicMaterial({ 
			color: 0x7b68ee,
			transparent: true,
			opacity: 0.8
		});

		for (let i = 0; i < 20; i++) {
			const orb = new THREE.Mesh(orbGeometry, orbMaterial);
			orb.position.set(
				(Math.random() - 0.5) * 10,
				(Math.random() - 0.5) * 10,
				(Math.random() - 0.5) * 10
			);
			orb.userData = { 
				originalY: orb.position.y,
				floatSpeed: Math.random() * 0.02 + 0.01
			};
			scene.add(orb);
		}

		// Thai temple silhouette
		const templeGeometry = new THREE.BoxGeometry(2, 1.5, 0.1);
		const templeMaterial = new THREE.MeshBasicMaterial({ 
			color: 0xd4af37,
			transparent: true,
			opacity: 0.3
		});
		const temple = new THREE.Mesh(templeGeometry, templeMaterial);
		temple.position.set(0, -2, -5);
		scene.add(temple);

		camera.position.z = 5;
	}

	function createSpiritsScene() {
		// Different types of Thai spirits
		const spiritTypes = [
			{ color: 0xff0000, size: 0.3 }, // Phi Pop
			{ color: 0x00ff00, size: 0.2 }, // Phi Tai Hong
			{ color: 0x0000ff, size: 0.4 }, // Krasue
		];

		spiritTypes.forEach((type, index) => {
			const geometry = new THREE.SphereGeometry(type.size, 8, 8);
			const material = new THREE.MeshBasicMaterial({ 
				color: type.color,
				transparent: true,
				opacity: 0.7
			});
			const spirit = new THREE.Mesh(geometry, material);
			spirit.position.set((index - 1) * 3, 0, 0);
			spirit.userData = { rotationSpeed: Math.random() * 0.05 + 0.01 };
			scene.add(spirit);
		});

		camera.position.z = 8;
	}

	function createRitualScene() {
		// Ritual circle
		const circleGeometry = new THREE.RingGeometry(1, 1.2, 32);
		const circleMaterial = new THREE.MeshBasicMaterial({ 
			color: 0xd4af37,
			transparent: true,
			opacity: 0.6,
			side: THREE.DoubleSide
		});
		const circle = new THREE.Mesh(circleGeometry, circleMaterial);
		circle.rotation.x = -Math.PI / 2;
		scene.add(circle);

		// Candles
		for (let i = 0; i < 8; i++) {
			const angle = (i / 8) * Math.PI * 2;
			const candleGeometry = new THREE.CylinderGeometry(0.05, 0.05, 0.3);
			const candleMaterial = new THREE.MeshBasicMaterial({ color: 0xffffff });
			const candle = new THREE.Mesh(candleGeometry, candleMaterial);
			candle.position.set(Math.cos(angle) * 1.5, 0.15, Math.sin(angle) * 1.5);
			scene.add(candle);

			// Flame
			const flameGeometry = new THREE.SphereGeometry(0.03, 8, 8);
			const flameMaterial = new THREE.MeshBasicMaterial({ 
				color: 0xff6b35,
				transparent: true,
				opacity: 0.8
			});
			const flame = new THREE.Mesh(flameGeometry, flameMaterial);
			flame.position.set(Math.cos(angle) * 1.5, 0.35, Math.sin(angle) * 1.5);
			flame.userData = { flickerSpeed: Math.random() * 0.1 + 0.05 };
			scene.add(flame);
		}

		camera.position.set(0, 3, 3);
		camera.lookAt(0, 0, 0);
	}

	function animate() {
		animationFrame = requestAnimationFrame(animate);

		// Animate objects based on scene type
		scene.children.forEach((child) => {
			if (child.userData.floatSpeed) {
				child.position.y = child.userData.originalY + Math.sin(Date.now() * child.userData.floatSpeed) * 0.5;
			}
			if (child.userData.rotationSpeed) {
				child.rotation.y += child.userData.rotationSpeed;
			}
			if (child.userData.flickerSpeed) {
				const scale = 1 + Math.sin(Date.now() * child.userData.flickerSpeed) * 0.2;
				child.scale.setScalar(scale);
			}
		});

		renderer.render(scene, camera);
	}

	function handleResize() {
		if (camera && renderer && canvas) {
			camera.aspect = canvas.clientWidth / canvas.clientHeight;
			camera.updateProjectionMatrix();
			renderer.setSize(canvas.clientWidth, canvas.clientHeight);
		}
	}
</script>

<svelte:window on:resize={handleResize} />

<canvas 
	bind:this={canvas} 
	class="w-full h-full"
	style="display: block;"
></canvas>