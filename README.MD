
# Reponsive website with Flexbox and Sass.

This repo contains a web site which I created by following an online flexbox tutorial from udemy. I creating this repo so I can have refrence to CSS properties and tricks which I learned following the course.

## Notes to self.

 - Set margin on flex item to divide them into groups [example](https://medium.com/@iamryanyu/how-to-align-last-flex-item-to-right-73512e4e5912)
 - Set media queries in descending order for example see the `sass` file
 - Use CSS not operator with :last-child e.g:
`
&:not(:last-child) {
margin-bottom:  .5rem;
}
`
 - Use CSS variable
 variable assignment syntax
`
:root {
  --color-primary: #eb2f64;
}`
accessing the variable
`color: var(--color-primary);`
- Set font-size on body
when create website it's best to set font-size of 10px in percentages on body, so we can use rems easily throughout the web site. 16px is default size of browsers
`
font-size: 62.5%; // 1rem = 10px;  10px/16px = 62%
`
### Unit conversion from relative to absolute px
````
html, body {
    font-size: 16px;
    width: 80vw
}
header {
    font-size: 150%
    padding: 2em;
    margin-bottom: 10rem;
    height: 90vh;
    width: 1000px;
}
.header-child {
    font-size: 3em;
    padding: 10%;
}
````
|         | Example | How to Convert into PX            | Result in Px |
|---------|---------|-----------------------------------|--------------|
| %font   | 150%    | 150 * parents computed font size  | 24px         |
| %length | 10%     | 10% of parents computed __width__ | 100px        |

- When using percentage unit for font-size. It's relative to parents computed font-size
- When using percentage unit for length like (height, padding, margin etc) . It' relative to parents computed __width__

### Font based relative units
## em vs rem
-- both are font based.
-- em uses parent to current element as a reference whereas rem uis relative to root font-size

|              | Example (x) | How to convert into pixels              | Result in Pixels                  |
|--------------|-------------|-----------------------------------------|-----------------------------------|
| em (font)    | 3em         | 3 * parents computed font-size          | 72px (3 * 24px)                   |
| em (lengths) | 2em         | 2 * current elements computed font-size | 2em * 24px = 48px                 |
| rem          | 10rem       | 10 * root font size                     | 10 * 16px = 160px 16px is default |



- We can set font-size on html selctor to 100% this will cause 1rem = 16px because 16px is default browser font-size. Now if user changes the browser font-size it will be reflected through out the css. To make calculations easy for easy a good rule is to set 1rem = 10px we can do that by by setting `font-size: 62.5%` because 62.5% of 16px is 10px. Which makes 1rem = 10px.
    
## BEM
- Block Element Modifier
`block {}`
-- Blocks are standalone component which can be used anywhere in the project.
`block__element {}`
-- Element is part of a block. It does not have any standalone meaning.
`block__element--modifier {}`
-- different version of block or element.