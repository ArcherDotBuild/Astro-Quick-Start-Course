# Astro Quick Start Course

Teacher: Traversy Media

- https://github.com/bradtraversy/astro-blog

## 01. Install & Setup

- `npm create astro@latest`
- Empty
- Typescript? Yes
- TypeScript? Strict
- npx astro add tailwind

## 02. Image Component

- src image
- public image

```html
---
import { Image } from 'astro:assets'
import logo from '../images/logo.png'
---

<image
  src="{logo}"
  class="h-14"
  alt="TechPeople Logo"
  width="{55}"
  height="{65}"
/>

<image
  src="/images/image1.png"
  alt="Article Image"
  class="w-full h-auto rounded-2xl"
  width="{600}"
  height="{350}"
/>
```

## 03. Component Script

```javascript
---
const name = 'John Doe'
console.log(name);

const users = [
  {name: 'Goku', age: 36},
  {name: 'Gohan', age: 18},
  {name: 'Trunks', age: 19},
]
---

<h1>Hello {name}</h1>

<ul>
  {users.map((user) => (
    <li>{user.name}, {user.age}</li>
  ))}
</ul>

<script>
  const name = 'John Doe'
  console.log(name);
</script>
```
## 04. Layout & Slots

## 05. Component Props

`<MainLayout title='Articles, Stories & Tutorials For Tech People'>`  

## 06. Using Constants