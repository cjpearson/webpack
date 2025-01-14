# example.js

```javascript
import { resetCounter, print } from "./methods";

setTimeout(async () => {
	const counter = await import("./counter");
	print(counter.value);
	counter.increment();
	counter.increment();
	counter.increment();
	print(counter.value);
	await resetCounter();
	print(counter.value);
}, 100);
```

# methods.js

```javascript
export const resetCounter = async () => {
	(await import("./counter")).reset();
};

export const print = value => console.log(value);
```

# counter.js

```javascript
export let value = 0;
export function increment() {
	value++;
}
export function decrement() {
	value--;
}
export function reset() {
	value = 0;
}
```

# dist/output.js

```javascript
/******/ "use strict";
/******/ var __webpack_modules__ = ({});
```

<details><summary><code>/* webpack runtime code */</code></summary>

``` js
/************************************************************************/
/******/ // The module cache
/******/ var __webpack_module_cache__ = {};
/******/ 
/******/ // The require function
/******/ function __webpack_require__(moduleId) {
/******/ 	// Check if module is in cache
/******/ 	var cachedModule = __webpack_module_cache__[moduleId];
/******/ 	if (cachedModule !== undefined) {
/******/ 		return cachedModule.exports;
/******/ 	}
/******/ 	// Create a new module (and put it into the cache)
/******/ 	var module = __webpack_module_cache__[moduleId] = {
/******/ 		// no module.id needed
/******/ 		// no module.loaded needed
/******/ 		exports: {}
/******/ 	};
/******/ 
/******/ 	// Execute the module function
/******/ 	__webpack_modules__[moduleId](module, module.exports, __webpack_require__);
/******/ 
/******/ 	// Return the exports of the module
/******/ 	return module.exports;
/******/ }
/******/ 
/******/ // expose the modules object (__webpack_modules__)
/******/ __webpack_require__.m = __webpack_modules__;
/******/ 
/************************************************************************/
/******/ /* webpack/runtime/define property getters */
/******/ (() => {
/******/ 	// define getter functions for harmony exports
/******/ 	__webpack_require__.d = (exports, definition) => {
/******/ 		for(var key in definition) {
/******/ 			if(__webpack_require__.o(definition, key) && !__webpack_require__.o(exports, key)) {
/******/ 				Object.defineProperty(exports, key, { enumerable: true, get: definition[key] });
/******/ 			}
/******/ 		}
/******/ 	};
/******/ })();
/******/ 
/******/ /* webpack/runtime/ensure chunk */
/******/ (() => {
/******/ 	__webpack_require__.f = {};
/******/ 	// This file contains only the entry chunk.
/******/ 	// The chunk loading function for additional chunks
/******/ 	__webpack_require__.e = (chunkId) => {
/******/ 		return Promise.all(Object.keys(__webpack_require__.f).reduce((promises, key) => {
/******/ 			__webpack_require__.f[key](chunkId, promises);
/******/ 			return promises;
/******/ 		}, []));
/******/ 	};
/******/ })();
/******/ 
/******/ /* webpack/runtime/get javascript chunk filename */
/******/ (() => {
/******/ 	// This function allow to reference async chunks
/******/ 	__webpack_require__.u = (chunkId) => {
/******/ 		// return url for filenames based on template
/******/ 		return "" + chunkId + ".output.js";
/******/ 	};
/******/ })();
/******/ 
/******/ /* webpack/runtime/hasOwnProperty shorthand */
/******/ (() => {
/******/ 	__webpack_require__.o = (obj, prop) => (Object.prototype.hasOwnProperty.call(obj, prop))
/******/ })();
/******/ 
/******/ /* webpack/runtime/make namespace object */
/******/ (() => {
/******/ 	// define __esModule on exports
/******/ 	__webpack_require__.r = (exports) => {
/******/ 		if(typeof Symbol !== 'undefined' && Symbol.toStringTag) {
/******/ 			Object.defineProperty(exports, Symbol.toStringTag, { value: 'Module' });
/******/ 		}
/******/ 		Object.defineProperty(exports, '__esModule', { value: true });
/******/ 	};
/******/ })();
/******/ 
/******/ /* webpack/runtime/import chunk loading */
/******/ (() => {
/******/ 	// no baseURI
/******/ 	
/******/ 	// object to store loaded and loading chunks
/******/ 	// undefined = chunk not loaded, null = chunk preloaded/prefetched
/******/ 	// [resolve, reject, Promise] = chunk loading, 0 = chunk loaded
/******/ 	var installedChunks = {
/******/ 		0: 0
/******/ 	};
/******/ 	
/******/ 	__webpack_require__.f.j = (chunkId, promises) => {
/******/ 			// JSONP chunk loading for javascript
/******/ 			var installedChunkData = __webpack_require__.o(installedChunks, chunkId) ? installedChunks[chunkId] : undefined;
/******/ 			if(installedChunkData !== 0) { // 0 means "already installed".
/******/ 	
/******/ 				// a Promise means "currently loading".
/******/ 				if(installedChunkData) {
/******/ 					promises.push(installedChunkData[1]);
/******/ 				} else {
/******/ 					if(true) { // all chunks have JS
/******/ 						// setup Promise in chunk cache
/******/ 						var promise = import("./" + __webpack_require__.u(chunkId)).then((data) => {
/******/ 							var {ids, modules, runtime} = data;
/******/ 							// add "modules" to the modules object,
/******/ 							// then flag all "ids" as loaded and fire callback
/******/ 							var moduleId, chunkId, i = 0;
/******/ 							for(moduleId in modules) {
/******/ 								if(__webpack_require__.o(modules, moduleId)) {
/******/ 									__webpack_require__.m[moduleId] = modules[moduleId];
/******/ 								}
/******/ 							}
/******/ 							if(runtime) runtime(__webpack_require__);
/******/ 							for(;i < ids.length; i++) {
/******/ 								chunkId = ids[i];
/******/ 								if(__webpack_require__.o(installedChunks, chunkId) && installedChunks[chunkId]) {
/******/ 									installedChunks[chunkId][0]();
/******/ 								}
/******/ 								installedChunks[ids[i]] = 0;
/******/ 							}
/******/ 	
/******/ 						}, (e) => {
/******/ 							if(installedChunks[chunkId] !== 0) installedChunks[chunkId] = undefined;
/******/ 							throw e;
/******/ 						});
/******/ 						var promise = Promise.race([promise, new Promise((resolve) => (installedChunkData = installedChunks[chunkId] = [resolve]))])
/******/ 						promises.push(installedChunkData[1] = promise);
/******/ 					} else installedChunks[chunkId] = 0;
/******/ 				}
/******/ 			}
/******/ 	};
/******/ 	
/******/ 	// no on chunks loaded
/******/ })();
/******/ 
/************************************************************************/
```

</details>

``` js
var __webpack_exports__ = {};
/*!********************************!*\
  !*** ./example.js + 1 modules ***!
  \********************************/
/*! namespace exports */
/*! runtime requirements: __webpack_require__.e, __webpack_require__, __webpack_require__.* */

;// CONCATENATED MODULE: ./methods.js
const resetCounter = async () => {
	(await __webpack_require__.e(/*! import() */ 1).then(__webpack_require__.bind(__webpack_require__, /*! ./counter */ 1))).reset();
};

const print = value => console.log(value);

;// CONCATENATED MODULE: ./example.js


setTimeout(async () => {
	const counter = await __webpack_require__.e(/*! import() */ 1).then(__webpack_require__.bind(__webpack_require__, /*! ./counter */ 1));
	print(counter.value);
	counter.increment();
	counter.increment();
	counter.increment();
	print(counter.value);
	await resetCounter();
	print(counter.value);
}, 100);
```

# dist/output.js (production)

```javascript
var e,o={},t={};function r(e){var n=t[e];if(void 0!==n)return n.exports;var i=t[e]={exports:{}};return o[e](i,i.exports,r),i.exports}r.m=o,r.d=(e,o)=>{for(var t in o)r.o(o,t)&&!r.o(e,t)&&Object.defineProperty(e,t,{enumerable:!0,get:o[t]})},r.f={},r.e=e=>Promise.all(Object.keys(r.f).reduce(((o,t)=>(r.f[t](e,o),o)),[])),r.u=e=>e+".output.js",r.o=(e,o)=>Object.prototype.hasOwnProperty.call(e,o),r.r=e=>{"undefined"!=typeof Symbol&&Symbol.toStringTag&&Object.defineProperty(e,Symbol.toStringTag,{value:"Module"}),Object.defineProperty(e,"__esModule",{value:!0})},e={179:0},r.f.j=(o,t)=>{var n=r.o(e,o)?e[o]:void 0;if(0!==n)if(n)t.push(n[1]);else{var i=import("./"+r.u(o)).then((o=>{var t,n,{ids:i,modules:a,runtime:s}=o,u=0;for(t in a)r.o(a,t)&&(r.m[t]=a[t]);for(s&&s(r);u<i.length;u++)n=i[u],r.o(e,n)&&e[n]&&e[n][0](),e[i[u]]=0}),(t=>{throw 0!==e[o]&&(e[o]=void 0),t}));i=Promise.race([i,new Promise((t=>n=e[o]=[t]))]),t.push(n[1]=i)}};const n=e=>console.log(e);setTimeout((async()=>{const e=await r.e(946).then(r.bind(r,946));n(e.value),e.increment(),e.increment(),e.increment(),n(e.value),await(async()=>{(await r.e(946).then(r.bind(r,946))).reset()})(),n(e.value)}),100);
```

# Info

## Unoptimized

```
asset output.js 6.35 KiB [emitted] [javascript module] (name: main)
asset 1.output.js 1.36 KiB [emitted] [javascript module]
chunk (runtime: main) output.js (main) 420 bytes (javascript) 2.89 KiB (runtime) [entry] [rendered]
  > ./example.js main
  runtime modules 2.89 KiB 6 modules
  ./example.js + 1 modules 420 bytes [built] [code generated]
    [no exports]
    [no exports used]
    entry ./example.js main
    used as library export
chunk (runtime: main) 1.output.js 146 bytes [rendered]
  > ./counter ./methods.js 2:8-27
  > ./counter ./example.js 4:23-42
  ./counter.js 146 bytes [built] [code generated]
    [exports: decrement, increment, reset, value]
    import() ./counter ./example.js + 1 modules ./example.js 4:23-42
    import() ./counter ./example.js + 1 modules ./methods.js 2:8-27
webpack 5.40.0 compiled successfully
```

## Production mode

```
asset output.js 1.15 KiB [emitted] [javascript module] [minimized] (name: main)
asset 946.output.js 213 bytes [emitted] [javascript module] [minimized]
chunk (runtime: main) output.js (main) 420 bytes (javascript) 2.89 KiB (runtime) [entry] [rendered]
  > ./example.js main
  runtime modules 2.89 KiB 6 modules
  ./example.js + 1 modules 420 bytes [built] [code generated]
    [no exports]
    [no exports used]
    entry ./example.js main
    used as library export
chunk (runtime: main) 946.output.js 146 bytes [rendered]
  > ./counter ./methods.js 2:8-27
  > ./counter ./example.js 4:23-42
  ./counter.js 146 bytes [built] [code generated]
    [exports: decrement, increment, reset, value]
    import() ./counter ./example.js + 1 modules ./example.js 4:23-42
    import() ./counter ./example.js + 1 modules ./methods.js 2:8-27
webpack 5.40.0 compiled successfully
```
