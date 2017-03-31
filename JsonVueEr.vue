<template>
	<div :style="{ textIndent: '' + currentDepth + 'em' }">
		<template v-if="typeof( json ) === 'object' && ( maxDepth == 0 || ( currentDepth < maxDepth ) )">
			<a v-if="typeof( json ) === 'object'" @click="opened = !opened">
				<span>{{ opened ? '▼' : '▶︎' }}</span>
				<span>{{ Array.isArray( this.json ) ? 'array' : typeof( this.json ) }}</span>
				<span style="color: blue">{{ name }}</span>
				<span>{{ Object.keys( json ).length + " items" }}</span>
			</a>
			<template v-if="opened">
				<json-vue-er
					v-for="k in Object.keys( json )"
					key=k
					:max-depth="maxDepth"
					:current-depth="currentDepth + 1"
					:json="json[ k ]"
					:name="k"
				>
				</json-vue-er>
			</template>
		</template>
		<div v-else>
			<span>{{ Array.isArray( this.json ) ? 'array' : typeof( this.json ) }}</span>
			<span style="color: blue">{{ name }}</span>
			<span>{{ typeof( json ) == 'object' ? ( Object.keys( json ).length + " items" ) : json }} </span>
		</div>
	</div>
</template>

<script>
export default {
	name:		'json-vue-er'
,	props:	{ json: {}, name: { default: "" }, maxDepth: { default: 0 }, currentDepth:{ default: 0 } }
,	data()	{ return { opened: true } }
}
</script>

