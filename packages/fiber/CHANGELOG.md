# @react-three/fiber

## 8.0.19

### Patch Changes

- 360b45a: fix: handle attach on reconstruct

## 8.0.18

### Patch Changes

- be567c1: fix: suspense attach and three compat in webpack

## 8.0.17

### Patch Changes

- 9e3369e: fix dom resize, improve native tree shaking

## 8.0.16

### Patch Changes

- 669c45c: correctly type useLoader results

## 8.0.15

### Patch Changes

- c4715d5f: allow invalidate to preempt more than 1 frame

## 8.0.14

### Patch Changes

- 5559a119: Add support for recoverable errors

## 8.0.13

### Patch Changes

- 9d77d8e2: fix: detach attribute removal

## 8.0.12

### Patch Changes

- 3d10413f: fix portal layers

## 8.0.11

### Patch Changes

- 5167b1e4: memoized.args can be undefined

## 8.0.10

### Patch Changes

- eb321afd: fix: remount bug, allow portals to inject custom size

## 8.0.9

### Patch Changes

- 624df949: fix: canvas unmount race condition"

## 8.0.8

### Patch Changes

- 952a566: fix: react SSR

## 8.0.7

### Patch Changes

- f63806b: fix: react SSR

## 8.0.6

### Patch Changes

- d4bafb9: fix re-parenting, useframe not working properly in portals, attach crash

## 8.0.5

### Patch Changes

- 227c328: fix pointer for root and portals

## 8.0.4

### Patch Changes

- e981a72: fix: mock three color management, loosen peer dep

## 8.0.3

### Patch Changes

- 3252aed: setevents needs to spread and be mirrored in portals

## 8.0.2

### Patch Changes

- 8035d1f: fix: legacy mode

## 8.0.1

### Patch Changes

- 26db195: add legacy flag to turn of three.colormanagement

## 8.0.0

### Major Changes

- 385ba9c: v8 major, react-18 compat
- 04c07b8: v8 major, react-18 compat

### Patch Changes

- 347ea79: new beta for library testing

## 8.0.0-beta.0

### Major Changes

- 385ba9c: v8 major, react-18 compat

## 8.0.0-beta.0

### Patch Changes

- cf6316c: new beta for library testing

## 7.0.25

### Patch Changes

- 8698734: Release latest patches

## 7.0.24

### Patch Changes

- 7f46ddf: cleanup captured pointers when released (#1914)

## 7.0.23

### Patch Changes

- 30d38b1: remove logs

## 7.0.22

### Patch Changes

- 259e1fa: add camera:manual

## 7.0.21

### Patch Changes

- 65e4147: up usemeasure, add last event to internals"

## 7.0.20

### Patch Changes

- 54cb0fd: update react-use-measure, allow it to use the offsetSize

## 7.0.19

### Patch Changes

- 7aa2eab: fix: remove zustand subcribe selector

## 7.0.18

### Patch Changes

- 6780f58: fix unmount pointer capture

## 7.0.17

### Patch Changes

- 894c550: fix: event count

## 7.0.16

### Patch Changes

- c7a4220: patch: applyprops returns the same instance

## 7.0.15

### Patch Changes

- c5645e8: fix primitve leftovers on switch

## 7.0.14

### Patch Changes

- 05af996: fix: revert the is function

## 7.0.13

### Patch Changes

- f256558: fix(core): don't overwrite camera rotation
- 51e6fc9: fix(core): safely handle external instances

## 7.0.12

### Patch Changes

- 0df6073: fix: missed events

## 7.0.11

### Patch Changes

- 62b0a3a: fix: event order of missed pointers

## 7.0.10

### Patch Changes

- e019dd4: fixes

## 7.0.9

### Patch Changes

- cd266e4: Fix diffProps dashed keys

## 7.0.8

### Patch Changes

- 6f68406: Allow getCurrentViewport to receive an array

## 7.0.7

### Patch Changes

- 0375896: Simplify useframe, support instanced event cancelation, silence disposal

## 7.0.6

### Patch Changes

- fb052ad: Fix babel-env browserslist transpiling into old code"

## 7.0.5

### Patch Changes

- c97794a: Add useLoader.clear(Loader, input)

## 7.0.4

### Patch Changes

- 974ecfb: Allow elements to define attachFns for specific mount/unmount

## 7.0.2

### Patch Changes

- a97aca3: Add controls state field
- 4c703d6: fix rttr didn't work with r130

## 7.0.0

### Major Changes

- 96ae1ad: fix javascript interpreting negative renderpriority as positive

This is a major breaking change that will fix an edge-case. It will only affect you if you used negative useFrame indicies, for instance

```jsx
useFrame(..., -1)
```

Surprisingly this disabled auto-rendering although the documentation says positive numbers only. As of v7 this will not take over the render loop.

```jsx
function Render() {
  // Takes over the render-loop, the user has the responsibility to render
  useFrame(({ gl, scene, camera }) => {
    gl.render(scene, camera)
  }, 1)

function RenderOnTop() {
  // This will render on top of the previous call
  useFrame(({ gl, ... }) => {
    gl.render(...)
  }, 2)

function A() {
  // Will *not* take over the render-loop, negative indices can still be useful for sorting
  useFrame(() => ..., -1)

function B() {
  // B's useFrame will execute *after* A's
  useFrame(() => ..., -2)
```

## 6.2.3

### Patch Changes

- 26bc7eb: typescript changes

## 6.2.2

### Patch Changes

- 4f44a2c: use more helpful name with event handling in rttr

## 6.2.1

### Patch Changes

- Fix stopPropagation logic

## 6.2.0

### Minor Changes

- Allow object3d instances to be attached

## 6.1.5

### Patch Changes

- fix(rttr): if children is undefined return an array to map with

## 6.1.4

### Patch Changes

- 6faa090: Add shape to types, exclude event functions from event data

## 6.1.3

### Patch Changes

- 71e72c0: Fix constructor args with attached children (#1348)
- 015fc03: Only set up pointer/wheel events as passive
- a160e08: Fix event setPointerCapture and stopPropagation.

## 6.1.2
