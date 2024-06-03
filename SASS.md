<h1><img width="200px" alt="Sass" src="https://rawgit.com/sass/sass-site/main/source/assets/img/logos/logo.svg" /></h1>

# SASS - Syntactically Awesome Stylesheets (2006)

<img width="140px" height="120px" alt="img" src="https://gifdb.com/images/high/slapping-another-pikachu-pokemon-z4ad46l8peasx76k.gif" align="right" />


- ### It is a language that can extend `CSS` with superpowers
- ### If we attempt to build with plain `CSS`, we often end up repeating.
- ### SASS provide a compiler that allows us to write `CSS` in different languages.
<br>


<h3>(i) .sass </h3>



<p style="font-size: 16px;"> removes ; and {} </p>

```sass
nav
    ul
        margin: 0
        padding: 0
    li
        display: flex

```


<h3>(ii) .scss</h3>

<p style="font-size: 18px;">We can write regular CSS then extend it with additional features as needed.</p>


### Features

1. <h4>$ Variables</h4>

    - use $ sign to name a variable and reference it somewhere else in the code
    - if that value changes, we just need to update one line of code.

     ```scss
        $red: hsl(0, 100%, 50%);

        .button.danger {
            color: $red;
            border: 1px solid $red;
        }
    ```

2. <h4>Nesting</h4>
    
    - classes are often duplicated over again and again
    - to avoid this duplication we can do nesting inside the parent.
    - by default these classes will apply to descendant elements or can be applied to direct sibling using `&` which is a tool that tell `SASS` to combine the parent to the nested child.

    <table>
    <tr>
    <th><img height="40px" src="https://img.icons8.com/?size=100&id=21278&format=png&color=000000"></th>
    <th><img height="30px" alt="Sass" src="https://rawgit.com/sass/sass-site/main/source/assets/img/logos/logo.svg" /></th>
    </tr>
    <tr>
    <td>
    
    ```css
    .button .success {
        color: green;
    }


    .btn:focus {}

    .btn:hover {}

    ```
    
    </td>
    <td>

    ```scss
    .button {
        .success {
            color: green;
        }
    }
    .btn {
        &:focus {}
        &:hover {}
    }
    ```

    </td>
    </tr>
    </table>


3. <h4>Mixins</h4>

    - In `CSS` we often end up including similar group of styles on multiple classes
    - Mixin allows us to encapsulate similar style and apply those styles anywhere in the code using the `@include` keyword
    - It also takes arguments to create a large number of similar classes programmatically.

    ```scss
    @mixin cool-btn($color, $bg) {
        display: flex;
        color: $color;
        background: $bg;
    }

    .btn-orange {
        @include cool-btn(black, orange);
    }
    ```

4. <h4>Functions</h4>

    - Help to write more programmatic code.
    - use `if else` for conditional logic 
    ```scss
    @mixin theme-color($theme) {
        @if $theme == 'light' {
            background-color: $light;
        } @else {
            background-color: $dark;
        }
    }
    ```
    or create an array of values with variables then loop over them with each.
    ```scss
    $sizes: 40px, 50px, 80px;
    
     @each $size in $sizes {
        .icon-#{$size} {
            font-size: $size;
        }
     }
    ```

    - provides built in function `lighten / darken`
    ```scss
    $base-color: green;
    .card {
        background: lighten($base-color, 25%);
        color: darken($base-color, 25%);
    }
    ```

<h4>After all that compiler convert the code to valid `CSS` that can be use on browser. </h4>

### Install SASS
We can install `SASS` on Windows, Mac, or Linux by downloading the package for respective operating system.
If using Node.js, we can also install `SASS` using npm by running


```
npm install -g sass
```
