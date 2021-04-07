---
title: "Second"
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

> ## Practice
>
> The only way to get better at writing equations in LaTeX is with practice.
> Get the following equations working in a sample document.
>
> 1. $$r = \sqrt{x^2 + y^2}$$
> 2. $$\partial_x = \frac{\partial}{\partial x}$$
>    
>    (Hint: `\partial`)
> 3. $$\frac{\delta (xy)}{xy} = \sqrt{\left(\frac{\delta x}{x}\right)^2 + \left( \frac{\delta y}{y}\right)^2}$$
> 4. $$r_n = \left(\sum_i x_i^2\right)^{\frac{1}{2}}$$
> 5. $$\mathbf{r} = x\hat{\mathbf{i}} + y\hat{\mathbf{j}} + z\hat{\mathbf{k}}$$
>
>    (Hint: `\mathbf`, `\hat`)
> 6. $$a_\mathrm{radial} = \frac{v_\mathrm{tangential}^2}{r}$$
> 7. $$R_{\mu\nu} - \frac{1}{2}Rg_{\mu\nu} + \Lambda g_{\mu\nu} = \frac{8\pi G}{c^4} T_{\mu\nu}$$
> 8. $$\begin{align}
  \nabla \cdot \mathbf{E} &= \frac{\rho}{\varepsilon_0} &
  \nabla \cdot \mathbf{B} &= 0 \\
  \nabla \times \mathbf{E} &= -\frac{\partial \mathbf{B}}{\partial t} &
  \nabla \times \mathbf{B} &= \mu_0 \left( \mathbf{B} + \varepsilon_0 \frac{\partial \mathbf E}{\partial t}\right)
\end{align}$$
>    
>    (Hint: `\cdot`, `\varepsilon`)
>
> > ## Answers
> > 
> > 1. `$r = \sqrt{x^2 + y^2}$`
> > 2. `$\partial_x = \frac{\partial}{\partial x}$`
> > 3. `$\frac{\delta (xy)}{xy} = \sqrt{\left(\frac{\delta x}{x}\right)^2 + \left( \frac{\delta y}{y}\right)^2}$`
> > 4. `$r_n = \left(\sum_i x_i^2\right)^{\frac{1}{2}}$`
> > 5. `$\mathbf{r} = x\hat{\mathbf{i}} + y\hat{\mathbf{j}} + z\hat{\mathbf{k}}$`
> > 6. `$a_\mathrm{radial} = \frac{v_\mathrm{tangential}^2}{r}$`
> > 7. `$R_{\mu\nu} - \frac{1}{2}Rg_{\mu\nu} + \Lambda g_{\mu\nu} = \frac{8\pi G}{c^4} T_{\mu\nu}$`
> > 8. ` `
> > 
> > ~~~
> > \begin{align}
> > \nabla \cdot \mathbf{E} &= \frac{\rho}{\varepsilon_{0}} &
> > \nabla \cdot \mathbf{B} &= 0 \\
> > \nabla \times \mathbf{E} &= -\frac{\partial \mathbf{B}}{\partial t} &
> > \nabla \times \mathbf{B} &= \mu_{0} \left( \mathbf{B} + \varepsilon_{0} \frac{\partial \mathbf E}{\partial t}\right)
> > \end{align}
> > ~~~
> > {: .tex}
> {: .solution}
{: .challenge}

> ## Sequential indices in General Relativity
>
> In General Relativity (and possibly some other fields), indices must be
> kept in order; you can't have indices one above the other like LaTeX
> does. For example, $$\Gamma^c_{ab}$$ (`$\Gamma^c_{ab}$`) isn't valid.
>
> How can you make these display properly; i.e. as $$\Gamma^c{}_{ab}$$?
>
> > ## Answer
> >
> > The trick is to add an empty `{}` to hang the successive indices off; i.e.
> >
> > ~~~
> > $\Gamma^c{}_{ab}$
> > ~~~
> > {: .tex}
> >
> > (If you ever have very tall objects so this fails, then you'll need to look up `\vphantom`.)
> {: .solution}
{: .challenge}

{% include links.md %}
