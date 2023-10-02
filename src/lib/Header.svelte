<script lang="ts">
	import { page } from '$app/stores';
	import logo from '$lib/images/svelte-logo.svg';
	import github from '$lib/images/github.svg';
	import { Tabs } from 'flowbite';


	export const Step = { Step1: "Design", step2:"Text", step3:"FnPaint", step4:"LED", step5:"Holder" };
	export let currentStep = step2;

	function openCity(evt, cityName) {
		// Declare all variables
		var i, tabcontent, tablinks;

		// Get all elements with class="tabcontent" and hide them
		tabcontent = document.getElementsByClassName("tabcontent") as HTMLCollectionOf<HTMLElement>;
		for (i = 0; i < tabcontent.length; i++) {
			tabcontent[i].style.display = "none";
		}

		// Get all elements with class="tablinks" and remove the class "active"
		tablinks = document.getElementsByClassName("tablinks");
		for (i = 0; i < tablinks.length; i++) {
			tablinks[i].className = tablinks[i].className.replace("active", "");
		}

		// // Show the current tab, and add an "active" class to the button that opened the tab
		(document.getElementById(cityName) as HTMLElement).style.display = "block";
		evt.currentTarget.className = "tablinks active";
		console.log(evt.currentTarget.className);

		//(document.getElementById("defaultOpen") as HTMLElement).click();

		}
</script>

<header class="flex flex-col h-full" style="text-align:center">

	<div>

		<!-- Tab links -->
		<ul class="tab">
			<button class="tablinks" on:click={(evt)=>openCity(evt, 'Design')}>1.디자인</button>
			<button class="tablinks" on:click={(evt)=>openCity(evt, 'Text')}>2.글자</button>
			<button class="tablinks" on:click={(evt)=>openCity(evt, 'FnPaint')}>3.색상/마감</button>
			<button class="tablinks" on:click={(evt)=>openCity(evt, 'LED')}>4.LED</button>
			<button class="tablinks" on:click={(evt)=>openCity(evt, 'Holder')}>5.홀더</button>
		</ul>
		
		<!-- Tab content -->
		<div id="Design" class="tabcontent">
			<h3>Design</h3>
			<p>London is the capital city of England.</p>
		</div>
		
		<div id="Text" class="tabcontent">
			<h3>Text</h3>
			<p>Paris is the capital of France.</p>
		</div>
		
		<div id="FnPaint" class="tabcontent">
			<h3>FnPaint</h3>
			<p>Tokyo is the capital of Japan.</p>
		</div>

		<div id="LED" class="tabcontent">
			<h3>Led</h3>
			<p>Tokyo is the capital of Japan.</p>
		</div>

		<div id="Holder" class="tabcontent">
			<h3>Holder</h3>
			<p>Tokyo is the capital of Japan.</p>
		</div>
	</div>
</header>


<style>
	/*//////////////////////////////////// Style the tab ///////////////////////////////////*/
	.tab {
	overflow: hidden;
	border: 1px solid #ccc;
	background-color: #f1f1f1;
	}

	/* Style the buttons that are used to open the tab content */
	.tab button {
	background-color: inherit;
	float: left;
	border: none;
	outline: none;
	cursor: pointer;
	padding: 14px 16px;
	transition: 0.3s;
	}

	/* Change background color of buttons on hover */
	.tab button:hover {
	background-color: #ddd;
	}

	/* Create an active/current tablink class */
	.tab button.active {
	background-color: #ccc;
	}

	/* Style the tab content */
	.tabcontent {
	display: none;
	padding: 6px 12px;
	border: 1px solid #ccc;
	border-top: none;
	}
	/* Go from zero to full opacity */
	@keyframes fadeEffect {
		from {opacity: 0;}
		to {opacity: 1;}
	}
	/*//////////////////////////////////// Style the tab ///////////////////////////////////*/


	
	header {
		display: flex;
		justify-content: space-between;
	}

	.corner {
		width: 3em;
		height: 3em;
	}

	.corner a {
		display: flex;
		align-items: center;
		justify-content: center;
		width: 100%;
		height: 100%;
	}

	.corner img {
		width: 2em;
		height: 2em;
		object-fit: contain;
	}

	nav {
		display: flex;
		justify-content: center;
		--background: rgba(255, 255, 255, 0.7);
	}

	svg {
		width: 2em;
		height: 3em;
		display: block;
	}

	path {
		fill: var(--background);
	}

	ul {
		position: relative;
		padding: 0;
		margin: 0;
		height: 3em;
		display: flex;
		justify-content: center;
		align-items: center;
		list-style: none;
		background: var(--background);
		background-size: contain;
	}

	li {
		position: relative;
		height: 100%;
	}

	li[aria-current='page']::before {
		--size: 6px;
		content: '';
		width: 0;
		height: 0;
		position: absolute;
		top: 0;
		left: calc(50% - var(--size));
		border: var(--size) solid transparent;
		border-top: var(--size) solid var(--color-theme-1);
	}

	nav a {
		display: flex;
		height: 100%;
		align-items: center;
		padding: 0 0.5rem;
		color: var(--color-text);
		font-weight: 700;
		font-size: 0.8rem;
		text-transform: uppercase;
		letter-spacing: 0.1em;
		text-decoration: none;
		transition: color 0.2s linear;
	}

	a:hover {
		color: var(--color-theme-1);
	}
</style>


<!--
<div class="button" style="text-align:center">
	{#each tabs as tab, index}
		<button
			class="tab tab-lifted"
			class:tab-active={activeTab == index}
			on:click={() => (activeTab = index)}>{tab}</button>
	{/each}
</div>
<div class="card" class:hidden={activeTab != 0}>Content 1</div>
<div class="card" class:hidden={activeTab != 1}>Content 2</div>
<div class="card" class:hidden={activeTab != 2}>Content 3</div>
<div class="card" class:hidden={activeTab != 3}>Content 4</div>
<div class="card" class:hidden={activeTab != 4}>Content 5</div>
-->