NPX: Install lasted → execute → remove package.

- CORS:
    
    Origin include http/https + domain + port  
    CORS implements in the server where resources placed to accept incoming requests  
    
- Data storing optimization
    
    Storing as an object instead of an array to get the right one easier.  
    Ex: data = { key1: {data1}, key2: {data2}}  
    instead of data = [{data1}, {data2}]
    

Think about reducing the amount of code changed in the future.

Think about how data flow (when read new project)