---
# try also 'default' to start simple
theme: apple-basic
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
background: https://source.unsplash.com/collection/94734566/1920x1080
# apply any windi css classes to the current slide
class: "text-center"
# https://sli.dev/custom/highlighters.html
highlighter: shiki
# show line numbers in code blocks
lineNumbers: false
# some information about the slides, markdown enabled
info: |
  ## About DDD
  Presentation By Saman

# persist drawings in exports and build
drawings:
  persist: false
---

# DDD?

A buisness First Approach

<div class="pt-12">
  <span @click="$slidev.nav.next" class="px-2 py-1 rounded cursor-pointer" hover="bg-white bg-opacity-10">
    Let's Dive In<carbon:arrow-right class="inline"/>
  </span>
</div>

<!--
The last comment block of each slide will be treated as slide notes. It will be visible and editable in Presenter Mode along with the slide. [Read more in the docs](https://sli.dev/guide/syntax.html#notes)
-->

---

# What is DDD?

**_Paul Watzlawick_** :

>      One cannot not have an architecture.

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

---

# What is DDD?

- 🎨 **Maintainability**
- 📝 **Mutual understanding**
- 🧑‍💻 **Stability**
- 🤹 **faster on-boadring** - embedding Vue components to enhance your expressions
  <br>
  <br>

Read more about [DDD](https://en.wikipedia.org/wiki/Software_architecture)

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

---

# Code Structure

<br/>
<br/>
<br/>
<br/>
<div grid="~ cols-2 gap-2" m="-t-2">

<img border="rounded" src="https://paper-attachments.dropbox.com/s_FFF03BC78A30F82D87BC808FDB0EDF1C5F5BFFCBAE30893C1E876130EE87343A_1604850068699_image.png">

<img border="rounded" src="https://paper-attachments.dropbox.com/s_FFF03BC78A30F82D87BC808FDB0EDF1C5F5BFFCBAE30893C1E876130EE87343A_1604850265609_image.png">
</div>

---

# An Example

```js
// index.js
module.exports = function ProductCatalogModule (moduleOptions) {
  this.extendRoutes((routes) => {
    routes.unshift({
      name: 'product',
      path: '/p/:slug/',
      component: path.resolve(themeDir, 'pages/Product.vue')
    });
  );
  // we can't register stores through Nuxt modules so we have to make a plugin
  this.addPlugin(path.resolve(__dirname, 'plugins/add-stores.js'))
}
```

---

# An Example

```js
// plugins/add-stores.js
import CategoryStore from "../stores/category.js";
import ProductStore from "../stores/product.js";

export default async ({ store }) => {
  store.registerModule(CategoryStore);
  store.registerModule(ProductStore);
};
```

---

# An Example

```ruby
# Folder Structure            # Business Domain
src/
├─┬─ app/
│ ├─┬─ connector/
│ │ └─── api.js               # General
│ ├─┬─ model/
│ │ ├─── store.js             # General
│ │ └─── userModule.js        # General
│ ├─┬─ router/
│ │ ├─── router.js            # General
│ │ └─── routes.js            # General
│ └─┬─ ui/
│   └─── App.vue              # General
├─┬─ homepage/
│ └─┬─ ui/
│   └─── Home.vue             # Homepage
├─┬─ profile/
│ ├─┬─ images/
│ │ └─── defaultAvatar.png    # Profile
│ ├─┬─ model/
│ │ └─── profileModule.js     # Profile
│ └─┬─ ui/
│   ├─── Avatar.vue           # Profile
│   └─── Profile.vue          # Profile
└─┬─ settings/
  ├─┬─ images/
  │ └─── gearIcon.svg         # Settings
  ├─┬─ model/
  │ └─── settingsModule.js    # Settings
  └─┬─ ui/
    └─── Settings.vue         # Settings
```

---

# An Example

```ruby
# Folder Structure            # Business Domain
src/
├─┬─ components/
│ ├─── App.vue                # General
│ ├─── Avatar.vue             # Profile
│ ├─── Home.vue               # Homepage
│ ├─── Profile.vue            # Profile
│ └─── Settings.vue           # Settings
├─┬─ images/
│ ├─── gearIcon.svg           # Settings
│ └─── defaultAvatar.png      # Profile
├─── router/
│ ├─── router.js              # General
│ └─── routes.js              # General
├─┬─ store/
│ ├─── profileModule.js       # Profile
│ ├─── settingsModule.js      # Settings
│ ├─── store.js               # General
│ └─── userModule.js          # General
└─┬─ util/
  └─── api.js                 # General
```

---

# Learn More from refrences

[Domain-Driven Design in Nuxt Apps](https://vueschool.io/articles/vuejs-tutorials/domain-driven-design-in-nuxt-apps/) · [Software architecture](https://en.wikipedia.org/wiki/Software_architecture) · [Domain-Driven Design in Nuxt Apps](https://medium.com/bauer-kirch/a-domain-driven-vue-js-architecture-77771c20f0da)
