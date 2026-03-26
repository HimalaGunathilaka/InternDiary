
## React component
```tsx
function DoSomething() {
  console.log("Doing something...");
}
<DoSomething></DoSomething>
```
Is same as,
```tsx
function DoSomething() {
  return <div>Hello</div>;
}
```

---
```tax
<DoSomething />   // ✅ Component
<dosomething />   // ❌ Treated as HTML tag (like <div>)
```
---

## React Hook
Hooks let you use React features **inside functional components** (without classes).
> [!note] **useState** -- Persistant storage (But only until page reloads)
> ![[Pasted image 20260325135236.png]]



> [!note] **useEffect** -- React to changes (side effects)
> ![[Pasted image 20260325135333.png]]
> - If array empty its run once on mount.


