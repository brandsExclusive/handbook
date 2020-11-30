# Frontend Conventions

Marcel and Robert to document the most important things new contributors should know

The unwritten rules of customer portal development:
- React lifecycle methods should not be arrow functions
- Avoid using anonymous functions for callbacks
- Try have a meaningful key for react elements - try not to use index
- Spread remaining props on a jsx element at the top so it doesn't overwrite (unless explicitly need to)
- Avoid multi line ternary statements and ternary statements in JSX
- File name should match component name
- One component per file
- Components should use either function syntax or set a `displayName`
- name your "internal" component props `Props`, if you want to export this - provide a friendly external name and extend the original Props
- Avoid using the react-redux `useSelector` hook, but can use the `useDispatch`
- Index files should not be components
- Try avoid index files entirely, it's an old node concept that doesn't need to translate into front end
- Give components meaningful names that can identify them stand alone
- Treat every object as immutable by default, mutation should be very rare
- Avoid 'sub render' functions. Big trees can be fine sometimes and if you want to add a sub render, it should probably be another component
- Where possible, try use native methods
- Use `Set` to de-dupe items
- Use `Set` to check if something exists, it's O(1) to check instead of .find's O(n)
- Consider memoizing transforms that rarely change
- Avoid async calls in components, instead, do it in an action
- Components should not determine whether they render or not, that's up to the parent
- Most lodash array convenience methods are provided in the array utils, use them!
- Reducers should have as little logic as possible, logic belongs in the actions
- Avoid new references on every render
- Lift 'static' items outside of the component so they are not re-created on every render
- Async actions should use the 'API_CALL' action type
- Prefer margin left/margin top over right/bottom
- Atoms/Molecules/Orgamisms is for common components. If it's not used in multiple places, it probably belongs with the implementation
- Build components to be used in isolation, not how a parent intends to use them
- One way data flow with flux
- Parent elements should be in charge on laying out child elements the majority of the time
- Use classes to trigger different conditions, not passing JS variables to styled components