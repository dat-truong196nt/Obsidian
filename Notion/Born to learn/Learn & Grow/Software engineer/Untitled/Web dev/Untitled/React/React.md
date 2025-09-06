- React concepts
    
    - Single page application.
    
    - Imperative vs Declarative
        
        I_mperative code tells the computer how to do things_  
         and _declarative program focuses on what you want from the computer_.
        
    - Don’t touch the DOOM. React will do it.
        - Before React, we directly change the DOM to make the web dynamic.
        - The instruction, blueprint (JS Object) we send to React forms a virtual DOM.  
            From this virtual DOM, react will manipulate DOM for us.
    - Component Architecture
        
        - Small components form bigger components. Big components form a page.  
        - Components: Self-contained HTML, CSS, JS and just JS objects.  
        - Bind the component to its concern (Only do 1 thing) to be reusable.
        
    - One way data flow
        
        - The state is not directly changed, using `setState` instead.  
        - Data is read-only when rendering.  
        - Restriction for better debugging.
        
    - UI Library
        
        React is not a Framework. Install all the needed things you want.  
        We can use React core to make UI for other platforms (React core is  
        - React core + React DOM → Web.  
        - React core + React phone → React Native.  
        - React core + React desktop → Electron.  
        - React core + React AR/VR → React 360.  
        - React core + React terminal → React to blessed.
        
    
      
    
- How to become a good React developer
    
    - Decide on components
        
        How to break down the app into components? How to break down components to smaller ones?  
        How do we build reusable components?
        
    
    Device the state and where it lives
    
    - What changes when state changes
        
          
        
- Libraries
    - react
        
        The engine that runs how these applications get built.
        
    - react-dom
        
        Specifying that the engine should be directed to the web app
        
    - Babel and Webpack
        
        Babel:  
        - Convert ES6+ to ES5 where all web-browsers can understand.  
        - Used in FE + BE.  
        Webpack:  
        - Has 2 set of functionality: Loaders + Plugins  
        - Loaders transform source code.  
        SASS → CSS, CSS to HTML style, ES6+ → ES5 (Babel)  
        - Plugins do more than just transform files  
        Uglify, HotModuleReplacement, Chunk  
        - Heavily used in FE, cause we need to minify files to make pages load faster.  
        - Only be used in BE for Server-side rendering.
        
- JSX
    
    key: Help react know which one changed and only render the changes.
    
- API
    - URL parameters
- LifeCycle
    
    If the state changes, the component that inits the state will be updated.  
    Whenever the component gets updated or rerendered, its children will be rerendered.
    
- HOC
    
    **a higher-order component is a function that takes a component and returns a new component.**
    
- Form
    
    Original form handling was hard to write, needs updating user input, validate, show errors, handling form submittion.