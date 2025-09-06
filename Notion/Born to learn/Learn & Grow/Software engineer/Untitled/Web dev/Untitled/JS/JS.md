- Use currying to precompute to save memory for multiple same computing.  
multiply = (a) ⇒ (b) ⇒ a*b;  
const multiplyBy5 = multiply(5)

- Advance object destructuring
    
    const state = {
    
    user: {currentUser: ''},
    
    cart: {hidden: false}
    
    }
    
    const mapStateToProp = ({user: {_currentUser_}, cart: {_hidden_} }) => ({currentUser, hidden})
    
    mapStateToProp(state)
    

![[92-6-use-cases-of-spread-with-array.jpeg]]