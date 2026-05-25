<h1 align="center">Welcome to createUniqueSharedComposable 👋</h1>

![GitHub License](https://img.shields.io/github/license/robertwang1001/createUniqueSharedComposable)
![GitHub commit activity](https://img.shields.io/github/commit-activity/w/robertwang1001/createUniqueSharedComposable)
![GitHub Actions Workflow Status](https://img.shields.io/github/actions/workflow/status/robertwang1001/createUniqueSharedComposable/release.yaml)
![GitHub Release](https://img.shields.io/github/v/release/robertwang1001/createUniqueSharedComposable)
![GitHub Release Date](https://img.shields.io/github/release-date/robertwang1001/createUniqueSharedComposable)
![GitHub Issues or Pull Requests](https://img.shields.io/github/issues/robertwang1001/createUniqueSharedComposable)
![GitHub watchers](https://img.shields.io/github/watchers/robertwang1001/createUniqueSharedComposable)
![GitHub forks](https://img.shields.io/github/forks/robertwang1001/createUniqueSharedComposable)
![GitHub Repo stars](https://img.shields.io/github/stars/robertwang1001/createUniqueSharedComposable)
![NPM Version](https://img.shields.io/npm/v/create-unique-shared-composable)
![NPM Type Definitions](https://img.shields.io/npm/types/create-unique-shared-composable)
![NPM Downloads](https://img.shields.io/npm/dw/create-unique-shared-composable)
![Node Current](https://img.shields.io/node/v/create-unique-shared-composable)

Create Vue3 unique shared composables based on keys.

This is similar to the [createSharedComposable](https://vueuse.org/shared/createSharedComposable/) and [createGlobalStates](https://vueuse.org/shared/createGlobalState/) of [vueuse](https://vueuse.org/), however, uses keys to create independent shared states.

## Install

Using pnpm:

```bash
pnpm add create-unique-shared-composable
```

Using yarn:

```bash
yarn add create-unique-shared-composable
```

Using npm:

```bash
npm install create-unique-shared-composable
```

## Usage

```javascript
import { createUniqueSharedComposable } from 'create-unique-shared-composable'

const useFoo = createUniqueSharedComposable((_) => {
  const counter = ref(0)
  const doubled = computed(() => counter.value * 2)
  return {
    counter,
    doubled
  }
})

const { counter, doubled } = useFoo('key')
const { counter: counter1, doubled: doubled1 } = useFoo('key')
const { counter: counter2, doubled: doubled2 } = useFoo('key2')

counter.value++
console.log(counter.value) // 1
console.log(doubled.value) // 2

console.log(counter1.value) // 1
console.log(doubled1.value) // 2

console.log(counter1.value) // 0
console.log(doubled1.value) // 0
```

## Contributing

Contributions are welcome! If you have ideas, bug fixes, or improvements, please open an issue or submit a pull request on the
[GitHub repository](https://github.com/robertwang1001/createUniqueSharedComposable).

Give a ⭐️ if this project helped you!

## License

This project is licensed under the MIT License. See the [LICENSE](./LICENSE) file for more details.
