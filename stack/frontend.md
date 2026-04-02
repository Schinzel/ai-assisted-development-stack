# Frontend Paradigms

## 1. SPA — Single Page Application
React, Vue, Angular. The client renders everything — virtual DOM, state management, routing in JS.

## 2. SSR — Server-Side Rendering
JTE, ERB, Blade, JSP. The server generates complete HTML per request.

## 3. HTML over the wire
HTMX, Hotwire/Turbo. The server sends HTML fragments that replace parts of the page.

## 4. SSG — Static Site Generation
Hugo, Astro, 11ty. HTML is pre-built at build time.

## 5. Islands
Astro Islands, Fresh. Static HTML with isolated interactive JS components.

## 6. Hybrid SSR/SPA
Next.js, Nuxt, SvelteKit. Server-renders the first page, then the client takes over as SPA.

## 7. Web Components
Built into the browser, framework-agnostic, shadow DOM.

## 8. Progressively enhanced HTML
Plain HTML with sprinkles of JS (Alpine.js, vanilla JS). Works without JS, enhanced with it.

# Ranked against our 10 parameters

## 1. HTML over the wire
HTMX, Hotwire
- High on all ten
- Explicit, thin, no build steps
- Minimal surface, declarative
- Few attributes, rich primitives
- AI writes HTML attributes, done

## 2. SSR
JTE, ERB, Blade
- High on most
- Code is output
- No build steps
- Slightly lower on declarativeness and rich primitives — templates vary in expressiveness

## 3. Progressively enhanced HTML
Alpine.js, vanilla JS
- High on thinness and explicitness
- Alpine.js x-on, x-show is almost as declarative as HTMX
- But requires two mental models (HTML + JS)

## 4. SSG
Hugo, 11ty
- Explicit output, but requires a build system
- Limited for dynamic content
- Medium on most parameters

## 5. Web Components
- Built into the browser (thin, no dependencies)
- But shadow DOM hides things (breaks explicitness)
- Verbose API (weak readability)
- Poor primitives

## 6. Islands
Astro Islands, Fresh
- Two mental models: static HTML + interactive JS
- The AI needs to know where the boundary is
- Medium on almost everything

## 7. Hybrid SSR/SPA
Next.js, Nuxt
- Hydration is magic
- Bundler, transpiler, state management
- Tries to be everything, breaks thinness and explicitness

## 8. SPA
React, Vue, Angular
- Low on almost everything
- Virtual DOM, bundler, state management, hooks, lifecycle
- Large cognitive surface, implicit everywhere
