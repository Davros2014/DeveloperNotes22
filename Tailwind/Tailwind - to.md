Yes, you _absolutely can_ create a reusable CSS class that encapsulates a combination of Tailwind utility classes — but Tailwind itself doesn’t support this out-of-the-box in the traditional CSS way like:

css

CopyEdit

`.my-class {   @apply flex justify-end mb-10; }`

### ✅ Recommended Way: Use `@apply` in a Custom CSS File

You can define your own custom class using Tailwind's `@apply` directive inside a CSS file (usually something like `styles.css` or within your component-based styling setup).

#### Example:

css

CopyEdit

`/* styles.css or a Tailwind-compatible stylesheet */ .btn-container {   @apply flex justify-end mb-10; }`

Then you can use it like this in your HTML or JSX:

html

CopyEdit

`<div class="btn-container">   <!-- content --> </div>`

### 🛠 Requirements:

- Tailwind must be set up with **PostCSS** or a build tool like **Vite, Webpack, or Next.js** that supports Tailwind and processes `@apply`.
    
- This doesn’t work in plain CSS files without Tailwind’s build step.
    

---

### ⚠️ Alternatives (less recommended)

#### 1. **Component-based abstraction**

If you’re using something like React, Vue, etc., you can abstract this into a component:

jsx

CopyEdit

`// ButtonContainer.jsx export default function ButtonContainer({ children }) {   return <div className="flex justify-end mb-10">{children}</div>; }`

#### 2. **Just use a regular CSS class (if not using @apply)**

This is possible, but loses Tailwind’s atomic nature:

css

CopyEdit

`.btn-container {   display: flex;   justify-content: flex-end;   margin-bottom: 2.5rem; /* equivalent of mb-10 */ }`

But this isn't considered idiomatic Tailwind, and you miss the benefits of consistency and purge optimization.

---

### ✅ TL;DR

Yes, use `@apply` to create utility-composed custom classes for repeated layouts like `flex justify-end mb-10` — it's the clean, Tailwind-native way to avoid repetition.

Would you like help setting that up in your project (like where to put it or how to structure your Tailwind config)?