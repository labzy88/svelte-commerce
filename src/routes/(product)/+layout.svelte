<script lang="ts">
import { Nav } from '$lib/theme-config'
import { PageTransitions, Footer } from '$lib/components'

export let data

let showCartSidebar = false
let openSidebar = false
</script>

<div class="{showCartSidebar || openSidebar ? 'h-screen overflow-hidden' : 'h-full'}">
	<div class="hidden lg:block">
		<Nav
			me="{data.me}"
			cart="{data.cart}"
			store="{data.store}"
			q="{data.q}"
			bind:showCartSidebar="{showCartSidebar}"
			bind:openSidebar="{openSidebar}" />
	</div>

	<PageTransitions url="{data.url}">
		<slot />
	</PageTransitions>

	<div class="hidden md:block">
		<Footer me="{data.me}" cart="{data.cart}" />
	</div>
</div>
