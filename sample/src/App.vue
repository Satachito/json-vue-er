<template>
	<div id="app">
		Simple one:<br />
		<br />
		<json-vue-er :json="{ a: 1, b: 2 }"></json-vue-er>
		<br />
		<br />
		Comprehensive one:<br />
		<br />
		DEPTH:<input v-model="depth" /><br />
		<json-vue-er 
			:json="json"
			name="(root)"
			:max-depth="depth"
		>
		</json-vue-er>
	</div>
</template>

<script>
import JsonVueEr from 'json-vue-er/JsonVueEr'

export default {
	components: { JsonVueEr }
,	data() { return { json: { a: 1, b: { a: 1 }, c: { b: { a: 1 } }, d: { c: { b: { a: 1 } } } }, depth: 0 } }
}
</script>

