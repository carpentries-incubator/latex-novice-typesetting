---
title: "Test file"
teaching: 0
exercises: 0
questions:
- "Key question: Why is typesetting a useful thing to know?"
- "Key question: How can I create a new typeset document?"
objectives:
- "First learning objective. How to create a new LaTeX project in Overleaf."
- "Second learning objective. Become familiar with the Overleaf ecosystem."
- "Third learning objective. Learn what the minimum requirements for a LaTeX document are."
keypoints:
- "First key point. Typesetting is used in many domains to convey information in a more readable format."
- "Second key point. Creating a new, minimal document requires a document declaration, a preamble, and a document body."
---
FIXME

<img src="/ep2/8953359364ca3fe19b596dfe36ae040f.svg" align=middle width=59.848635pt height=33.769394999999996pt/>

![](aeae4a0768dff2246e453a637b9d1ae2.svg)

> ## Practice
>
> The only way to get better at writing equations in LaTeX is with practice.
> Get the following equations working in a sample document.
>
> 1. ![](aeae4a0768dff2246e453a637b9d1ae2.svg)
> 2. <p align="center"><img src="8953359364ca3fe19b596dfe36ae040f.svg?invert_in_darkmode" style="width: 200px;"/></p>
>    
>    (Hint: `\partial`)
> 3. <p align="center"><img src="svgs/824b328daa69975e501682f8d3815118.svg" style="width: 200px;"/></p>
> 4. <p align="center"><img src="svgs/a8fbb54fb474f031c11e91d18f1d45e9.svg?invert_in_darkmode" style="width: 200px;"/></p>
> 5. <p align="center"><img src="svgs/72cebfd8cd87d68a5555c5d698a4581f.svg?invert_in_darkmode" /></p>
>
>    (Hint: `\mathbf`, `\hat`)
> 6. <p align="center"><img src="svgs/ff950807f895e923cac0c01bd2912bd2.svg?invert_in_darkmode" style="width: 200px;"/></p>
> 7. <p align="center"><img src="svgs/d83c766121dc8999460ba2edc0b910d1.svg?invert_in_darkmode" style="width: 200px;"/></p>
> 8. <p align="center"><img src="svgs/95e1565e929e5bb3127d6f5a32f48cbe.svg?invert_in_darkmode" style="width: 200px;"/></p>
>    
>    (Hint: `\cdot`, `\varepsilon`)
>
> > ## Answers
> >
> > 1. `<img src="svgs/1309f388b4a8d4bf190f37c89bfd0875.svg?invert_in_darkmode" align=middle width=99.037785pt height=30.173879999999972pt/>`
> > 2. `<img src="svgs/1cf65057bb9f1fda743a990e52c4012f.svg?invert_in_darkmode" align=middle width=55.99538999999999pt height=28.866750000000007pt/>`
> > 3. `<img src="svgs/58972d206e8c88e04c6a0c657a34dc4c.svg?invert_in_darkmode" align=middle width=176.23286999999996pt height=52.50267pt/>`
> > 4. `<img src="svgs/16dbd33316c7d9880ed0fa6669859e27.svg?invert_in_darkmode" align=middle width=103.17483000000001pt height=39.20664pt/>`
> > 5. `<img src="svgs/7e8582c9c6ab51087897e580497e8de4.svg?invert_in_darkmode" align=middle width=116.9982pt height=31.421609999999983pt/>`
> > 6. `<img src="svgs/dbae3ffd5eb2e6cb8e9aa1a5eec84ff9.svg?invert_in_darkmode" align=middle width=123.03653999999999pt height=40.43885999999999pt/>`
> > 7. `<img src="svgs/9a22780399dd1123f229dfd591237bc2.svg?invert_in_darkmode" align=middle width=226.65769499999996pt height=28.61198999999999pt/>`
> > 8. ` `
> >
> > ~~~
> > <p align="center"><img src="svgs/f8691df8f3ddb8c98466c8641070427d.svg?invert_in_darkmode" align=middle width=595.54275pt height=77.79634499999999pt/></p>
> > ~~~
> > {: .tex}
> {: .solution}
{: .challenge}

> ## Sequential indices in General Relativity
>
> In General Relativity (and possibly some other fields), indices must be
> kept in order; you can't have indices one above the other like LaTeX
> does. For example, <p align="center"><img src="svgs/aeae4a0768dff2246e453a637b9d1ae2.svg?invert_in_darkmode" align=middle width=23.098679999999998pt height=15.786935999999999pt/></p> (`<img src="https://rawgit.com/carpentries-incubator/latex-novice-typesetting (fetch/gh-pages/svgs/19cd81ae4e0c341484d9ef981850c6ae.svg?invert_in_darkmode" align=middle width=23.09868pt height=22.381919999999983pt/>`) isn't valid.
>
> How can you make these display properly; i.e. as <p align="center"><img src="svgs/1361fdb6fbf69a00899cb4757868243b.svg?invert_in_darkmode" align=middle width=29.795205pt height=14.1888285pt/></p>?
>
> > ## Answer
> >
> > The trick is to add an empty `{}` to hang the successive indices off; i.e.
> >
> > ~~~
> > <img src="svgs/ed1fae0804d1334f261fa2bac8742b38.svg?invert_in_darkmode" align=middle width=29.795205pt height=22.381919999999983pt/>
> > ~~~
> > {: .tex}
> >
> > (If you ever have very tall objects so this fails, then you'll need to look up `\vphantom`.)
> {: .solution}
{: .challenge}

{% include links.md %}
