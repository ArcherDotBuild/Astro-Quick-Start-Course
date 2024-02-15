# Astro Quick Start Course

Teacher: Traversy Media

- https://github.com/bradtraversy/astro-blog
- Video tutorial: https://www.youtube.com/watch?v=XoIHKO6AkoM

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

Set up AstroJS types: `npx astro sync`

## 07. Custom 404 Page

## 08. Collections & Markdown

## 09. Collection Schema

## 10. Querying Collections

## 11. Format & Sort By Date

## 12. Article Card Component

## 13. Homepage Articles

## 14. Most Recent Article

## 15. Slug & getStaticPaths

#### Static Website

```javascript
---
import MainLayout from '../../layouts/MainLayout.astro'
import { getCollection } from 'astro:content'
import type { CollectionEntry } from 'astro:content'

export async function getStaticPaths() {
  const allBlogArticles: CollectionEntry<'blog'>[] = await getCollection('blog')

  return allBlogArticles.map((entry) => ({
    params: {
      slug: entry.slug
    },
    props: {entry}
  }) )
}

const { entry } = Astro.props
---

<MainLayout>
  <h1>{entry.data.title}</h1>
</MainLayout>
```

## 16. SSR Config & Single Article

Console.log the slug in the terminal

```javascript
---
import MainLayout from '../../layouts/MainLayout.astro'
import { getEntry } from 'astro:content'

const { slug } = Astro.params

console.log(slug);
---

<MainLayout>
  <h1>Article</h1>
</MainLayout>
```

Printing the data in the console

```javascript
const { slug } = Astro.params

// console.log(slug);
if (slug === undefined) {
  throw new Error('Slug is required')
}

const entry = await getEntry('blog', slug)
console.log(entry)
```

## 17. Tags Component

## 18. Footer Tags

## 19. Search Page

## 20. API Endpoints

`http://localhost:4321/api/search.json?query=boundless`
`http://localhost:4321/api/search.json?query=test`

## 21. Pagination Component

## 22. Disable Prev & Next
