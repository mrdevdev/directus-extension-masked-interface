<script lang="ts">
import { useExtensions } from "@directus/extensions-sdk";
import { defineComponent } from "@vue/runtime-core";

export default defineComponent({
	setup(props, {attrs, emit}) {
		const { interfaces } = useExtensions();
		const { component: TranslationComponent } = interfaces.value.find(
		(i) => i.id === "translations"
		);
		return {
			attrs,
			TranslationComponent,
		};
	}
})
</script>

<template>
  <component :is="TranslationComponent" v-bind="attrs" />
  <h1>My Custom additions<h1>
</template>
