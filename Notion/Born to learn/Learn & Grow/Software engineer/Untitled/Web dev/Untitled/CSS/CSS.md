- Make your page cooler
    - perspective: 500px;
    - hyphens: auto;
- Đấng cứu thế
    - overflow: hidden;
    - backface-visibility: hidden;
    - display: inline-block;
- Responsive
    
    - ORDER: reset + typography -> general layout + grid -> page layout -> component.
    
    ![[Screenshot_from_2022-01-19_21-49-44.png]]
    
    - @media only screen and (hover: none): Choosing touch devices - usually combine with phone.
    - display: flex > margin-right: auto.
- SCSS
    
    **File structure**  
    7-1 pattern | 5-1 pattern
    
    ---
    
    - **==`abstracts`==** - don’t produce any CSS code
        
        _fonts.scss  
        _helpers.scss  
        _mixins.scss  
        _variables.scss  
        _animations.scss
        
    - ==`**base**`== - boilerplate codes - apply for all
        
        _reset.scss  
        _typography.scss
        
    - **`==components==` -** component-driven approach
        
        _button.scss  
        _form.scss  
        _card.scss
        
    - `**==layouts==**`
        
        _header.scss  
        _footer.scss  
        _navigation.scss
        
    - `**==pages==**`
        
        _home.scss
        
    - `**==themes==**`
        
        _dark.scss  
        _light.scss
        
    - `**==vendors==**`
        
        _bootstrap.scss
        
    
      
    
    **Responsive design:**
    
    ---
    
    - `**Fluid layouts**`
        
        - Adapt to the current `viewport width` (or even height).  
        - Use `%` (or `vh` / `vw`).  
        - Use max-width instead of width.
        
    - `**Responsive units**`
        
        - Use `rem` instead of `px`.
        
    - Flexible images
        
        - Image auto-scale to the viewport.  
        - Use `%` alongside with `max-width`.
        
    - Media queries
        
        - Change CSS styles on the specific viewport (breakpoints).
        

#### Pages

|Name|
|---|
|[[CSS in JS]]|