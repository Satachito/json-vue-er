# json-vue-er, a JSON viewer component in Vue.js.


* No external resources.
* Very fast. There is no data conversion inside.
* Ultra small. Easy to understand and modify.

## Installation

With npm:

```bash
npm install json-vue-er --save
```

In script tag

```javascript
import JsonVueEr from "../node_modules/json-vue-er/JsonVueEr"
```

## Sample

See 'sample' directory in the package.

Simple one:

```
export default {
	components: { JsonVueEr }
,	template	: '<json-vue-er :json="{ a: 1, b: 2 }"></json-vue-er>'
}
```

Comprehensive one:

```
export default {
	components: { JsonVueEr }
,	data()	{ return { json: "{ a: 1, b: [ 'A', 'B' ], c: [ 'A', 'B', 'C' ], d: [ 'A', 'B', 'C', 'D' ] }", depth: 0 } }
,	template: `
		<div>
			DEPTH:<input v-model="depth" /><br />
			<json-vue-er 
				:json="json"
				:name="(root)"
				:max-depth="depth"
			>
			</json-vue-er>
		</div>
	`
}
```


## Props

`json` - The JSON to be displayed. Expects a valid JSON object.<br />
`name` - The name of the root object.<br />
`max-depth` - The maximum level of the JSON Tree to be expanded. Specify 0 to Infinity.<br />
`current-depth` - Don't care. Current expantion level of the JSON tree.<br />

## Changelog

- 1.0.0: Initial Release

