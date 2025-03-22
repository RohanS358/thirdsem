
# Complex Analysis Notes

## Mappings

### Translation

- $w = f(z) = z + c$ where $c = a + ib$, $z = x + iy$
- $w = f(z) = z + i$
- $w = x + iy + i = (x + i)(y + i)$
- $u = x + 1$
- $v = y$

For rectangular domain with:

- $x, y = 0, 1$
- $u, v = 1, 2$
- $x, y = 1, 1$
- $u, v = 2, 1$

### Rotation

- $w = f(z) = ze^{i\theta}$ rotation
- Example: $x = 0, y = 0, x+iy = 2$ with rotation $\pi/4$
- $w = f(z) = ze^{i\pi/4}$
- $x+iy = ze^{i\pi/4}$
- $= (x+iy)[\cos(\pi/4) + i\sin(\pi/4)]$
- $= (x/\sqrt{2} - y/\sqrt{2}) + i(x/\sqrt{2} + y/\sqrt{2})$

Special cases:

- $x = 0, y = -y/\sqrt{2}, v = y/\sqrt{2}$ → $y = -v$ and $u+v = 0$
- $y = 0, u = x/\sqrt{2}, v = x/\sqrt{2}$ → $u-v = 0$
- $x+iy = 2, v = \sqrt{2}/\sqrt{2} = 1$

## Magnification

- $w = f(z) = cz$
- $z = x + iy$
- Find $u$ & $v$ and plot.

Example: $x = 0, y = 0, x = 1, y = 2$

- Find image $w = (1+i)z$

Working:

- $x^2 + y^2 - xy = 0$
- $\frac{u^2}{(u^2+v^2)^2} + \frac{2v}{(u^2+v^2)^2} + \frac{2v}{u^2+v^2} = 0$
- $1 + 2v = 0$
- $v = -1/2$

## Inversion

- $w = f(z) = 1/z$
- $w = 1/z$
- $\frac{x+iy}{u+iv} = \frac{u-iv}{u^2+v^2} = 1$
- $x = \frac{u}{u^2+v^2}$, $y = \frac{-v}{u^2+v^2}$
- $|z-1|^2 = 1$
- $|x+iy-1|^2 = 1$
- $x^2+(y-1)^2 = 1$
- $(0,1) \implies v = 1$

## Power Series

- $w = i^z$
- $\rho = i^{re^{i\theta}}$
- $= i^r(\cos\theta + i\sin\theta)$
- $= i^r e^{-\pi r \sin\theta/2 + i\theta}$
- Power series: $\sum_{n=0}^{\infty} \frac{z^n}{n!}(z-z_0)^n$

## Radius of Convergence

- For $\rho$ & radius of convergence:
- $\sum_{n=2}^{\infty} \frac{z^n}{n(\log n)^2}$
- $\frac{1}{\rho} = \lim_{n\to\infty} \frac{|a_{n+1}|}{|a_n|} = \lim_{n\to\infty} \frac{n\log^2n}{(n+1)\log^2(n+1)}$

## Circle of Convergence

Domain of convergence: $|z-z_0| < R$ is circle of convergence.