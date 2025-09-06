- Where to use
    
    Large state management.
    
    Sharing data through components (avoid props drilling).
    
    - Predictable state
        
        Single source of truth - one store.  
        The state is read-only.  
        Changes using the pure function (reducer).
        

- Reducers are pieces of state.

- In mapStateToProps, the react shallow check the prop.
    
    if (preVallue === currValue)  
    + primitive type ⇒ react won’t rerender  
    + object type ⇒ the address changed due to redux create a new state ⇒ trigger rerender
    
- redux-persist
    
    localStorage.getItem('persist:root')