
### what is a vector 
A set of numbers that represents a position in an coodinate system.  

**2d**: $\begin{pmatrix} x \\ y \end{pmatrix}$

**3d**: $\begin{pmatrix} x \\ y \\ z \end{pmatrix}$

You can imagine a vector as **arrows** in a **coordinate system**. 
They contain **instructions** on **how to reach one specific coordinate**. 
One **vector corresponds** to **one coordinate** and there are **no duplicates**. 

### calculating with vectors 

#### Addition & subtraction 


$\begin{pmatrix} x_1 \\ y_1 \end{pmatrix} + \begin{pmatrix} x_2 \\ y_2 \end{pmatrix} =\begin{pmatrix} x_1+x_2 \\ y_1+y_2 \end{pmatrix}$


#### Multiplication 

$\begin{pmatrix} x_1 \\ y_1 \end{pmatrix} * \begin{pmatrix} x_2 \\ y_2 \end{pmatrix} =\begin{pmatrix} x_1*x_2 \\ y_1*y_2 \end{pmatrix}$

$n\begin{pmatrix} x_1 \\ y_1 \end{pmatrix} = \begin{pmatrix} n(x_1) \\ n(y_1) \end{pmatrix}$


#### Division 

$\begin{pmatrix} x_1 \\ y_1 \end{pmatrix}:n = \begin{pmatrix} \frac{x_1}{n} \\ \frac{y_1}{n} \end{pmatrix}$


**Numbers** are mostly called **scaler**, because, for example in the case; $x*\vec{a}$ - $x$ **is scaling** $a$ in either the positiv or negative direction. 
If you **multiply** a vector **with** a **negative number**, lets say $x = -1.9$, first $x$ **inverts** and then it **scales** into the **negative**. 

Addition can be visualized and conceptualized VERY well through imagining two vectors as arrows; $\vec{a}$ and $\vec{b}$. 
If they are added together through addition, the **origin** of arrow $\vec{b}$ moves to the **head of arrow** $\vec{a}$ and so the new point in the coordinate system is them **both added** together. 

Another version of this is; 
$\vec{a}=\begin{pmatrix} 2 \\ 3 \end{pmatrix}$

$\vec{b}=\begin{pmatrix} 1 \\ -2 \end{pmatrix}$


If you **add them together** through the moving of base of $\vec{b}$ to tip of $\vec{a}$, you simply "walk" $2+1$ steps on the $x$ axis and $3+(-1)$ steps on the $y$ axis. 
You can simplify that through just directly walking $3$ steps on the $x$ axis and $2$ steps on the $y$ axis. 







$\hat{i}= x \text{ basis vector}$
$\hat{j}= y \text{ basis vector}$

A given vector $\vec{n}$ is **made out of** these **basis vectors** with help of a **scaler**; $\vec{n} =\begin{pmatrix} a*\hat{i} \\ b*\hat{j} \end{pmatrix}$ and so a vector **describes** the **sum** of **two scaled basis vectors**. 


The **sum** of **two vectors** combined with **two independent scalers** is called a **linear combination**: $a\vec{n} + b\vec{m}$


The **span** of a **linear combination** describes every point they can **reach** in the **coordinate system** 


If one **vector** in an **linear combination** is **redundant**, for example; if $\vec{n}$ and $\vec{m}$ in the combination $a\vec{n} + b\vec{m} + c\vec{k}$ point in the same direction, its **lineare dependencie** ($\vec{n}$ and $\vec{m}$ are **linear dependent**)
If this is not the case, theyre **linear independent**



#### The basis of a vector space is a set of linearly independent vectors that span the full space


The basis of a vector space with **X dimensions** is a **vector set** with **X linearly indipendent vectors**. 
The **span** of this **set** of **vectors** is the **whole vector space** and so **every** single vector in this space can be **defined** through this **set + scalers**. 