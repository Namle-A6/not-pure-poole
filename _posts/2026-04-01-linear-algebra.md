---
layout: post
title: Đường đến giải hệ phương trình 
date: 2026-03-28 05:14 +0800
last_modified_at: 2026-04-01 06:08:25 +0800
tags: [linear-algebra]
math: true
toc:  true
---


Dựa trên hai cuốn sách mà mình tự học là "Giáo trình: Nhập môn lý thuyết ma trận" và "Toán học cao cấp: Đại số và hình học giải tích". 

## 1. Lý thuyết tập hợp (hữu hạn)

**Định nghĩa 1.1**: 

> Tập hợp là một khái niệm cơ bản không được định nghĩa, mà được hiểu như là một sự tụ tập những sự vật hoặc những đối tượng nhất định (và thường có cùng một hoặc một số tính chất chung nào đó). Mỗi sự vật hoặc đối tượng đó được gọi là một phần tử  của tập hợp. 

**Ví dụ 1.2**: 

Tập hợp các số tự nhiên: 0, 1, 2, 3, ...

Tập hợp các số nguyên: ...-1, -2, 0, 1, 2, ...

Tập hợp thường được kí hiệu bởi các chữ cái in hoa, chẳng hạn như *X, Y, Z, ...* Phần tử thường được kí hiệu bởi chữ cái in thường *x, y, z, ...*

**Ví dụ 1.3**:

Tập hợp các số tự nhiên: \\\(\mathbb{N}\\\)

Tập hợp các số thực: \\\(\mathbb{R}\\\)

Nếu phần tử *x* thuộc tập hợp *X* thì ta kí hiệu là \\\(x \in X\\\). Nếu phần tử *x* không thuộc tập hợp *X* thì ta kí hiệu là \\\(x \notin X\\\). 


**Ví dụ 1.4**: Cho một tập hợp là các số tự nhiên \\\(\mathbb{N}\\\):

Phần tử 1 thuộc tập hợp các số tự nhiên \\\(\mathbb{N}\\\), kí hiệu 1 \\\(\in \mathbb{N}\\\).

Phần tử -1 không thuộc tập hợp các số số tự nhiên \\\(\mathbb{N}\\\), kí hiệu -1 \\\(\notin \mathbb{N}\\\).

Một tập hợp không chứa phần tử nào được gọi là tập rỗng, và được kí hiệu là \\\(\emptyset\\\). 

**Ví dụ 1.5**: Tập hợp nghiệm thực của phương trình \\\(x^2 + 1 = 0\\\) là tập hợp \\\(\emptyset\\\).

Để biểu diễn một tập hợp, ta có thể liệt kê các phần tử của tập hợp đó:

> $$X = \{x_1, x_2, \dots\}$$

**Ví dụ 1.6**: Tập hợp năm số tự nhiên \\\(\mathbb{N}\\\) đầu tiên được biểu diễn ở dạng liệt kê như sau:

$$\mathbb{N} = \{0, 1, 2, 3, 4, 5\}$$

Ta cũng có thể biểu diễn tập hợp bằng cách chỉ rõ các tính chất đặc trưng của các phần tử của tập hợp:

> $$X = \{x|P(x)\}$$

với *P(x)* là tính chất của phần tử thuộc tập hợp *X*.

**Ví dụ 1.7**: Tập hợp các số hữu tỉ \\\(\mathbb{Q}\\\) được biểu diễn bằng cách chỉ rõ tính chất đặc trưng của mỗi phần tử như sau: 

$$\mathbb{Q} = \{\frac{a}{b}|a, b \in \mathbb{Z}, b \ne 0\}$$

**Ví dụ 1.8**: Tập nghiệm của hệ phương trình 

$$\begin{cases}
  x + y + z = 1 \\
  x + 2y + 3z = 0
\end{cases}$$

là tập hợp:

$$S = \{(x, y ,x)| x, y, z \in \mathbb{R}, x + y + x = 1, x + 2y + 3z = 0\}$$

Để mô tả tập hợp một cách trực quan, người ta biểu diễn mỗi tập hợp bởi các điểm nằm trong một vòng phẳng mà ta gọi là biểu đồ Ven.

***

## 2. Ánh xạ 

Để nghiên cứu mối quan hệ giữa hai tập hợp, ta tập trung tìm hiểu các quy tắc cho tương ứng mỗi phần tử của tập hợp này với mỗi phần tử của tập hợp kia. Một lớp quy tắc như thế dẫn đến định nghĩa như sau.

**Định nghĩa 2.1**: 

> Cho *X* và *Y* là hai tập hợp khác rỗng. Một ánh xạ *f* từ *X* đến *Y* là một quy tắc cho tương ứng mỗi phần tử \\\(x \in X\\\) với một và chỉ một phần tử \\\(y \in Y\\\). Phần tử *x* được gọi là tạo ảnh của phần tử *y* qua ánh xạ *f*. Phần tử *y* được gọi là ảnh của phần tử *x* qua ánh xạ *f* và kí hiệu là *f(x)*.

Ánh xạ *f* từ *X* đến *Y* được kí hiệu là: 

> $$ f: X \to Y, x \mapsto y = f(x) $$

Tập *X* được gọi là tập nguồn hay tập xác định của ánh xạ *f*. Tập *Y* được gọi là tập đích.

**Ví dụ 2.2**: Cho \\\(f: \mathbb{R} \to \mathbb{R}, x \mapsto x^2\\\). 

Vì \\\(f(2) = f(-2) = 2^2 = (-2)^2 = 4\\\) nên 4 là ảnh của 2 và -2. Còn 2 và -2 đều là tạo ảnh của 4.

Từ **định nghĩa 2.1** về ánh xạ, ta có các khái niệm về đơn ánh, toàn ánh, song ánh. 

**Định nghĩa 2.3**: Cho \\\(f: X \to Y\\\) là một ánh xạ: 

> (i) Ánh xạ *f* được gọi là ***đơn ánh*** nếu \\\(\forall x_1, x_2 \in X, x_1 \ne x_2\\\) kéo theo \\\(f(x_1) \ne f(x_2)\\\). 

> (ii) Ánh xạ *f* được gọi là ***toàn ánh*** nếu với bất kỳ \\\(y \in Y\\\), \\\(\exists x \in X\\\) sao cho \\\(y = f(x)\\\). 

> (iii) Ánh xạ *f* được gọi là ***song ánh*** nếu ánh xạ *f* vừa là ***đơn ánh*** và đồng thời cũng là ***toàn ánh***.

**Ví dụ 2.4**: Cho \\\(f: [0;\infty] \to \mathbb{R}, x \mapsto x^2\\\)

Với \\\(x_1 = 1 \in [0;\infty]\\\) ta được \\\(y_1 = f(x_1) = 1^2 = 1 \in \mathbb{R}\\\)

Với \\\(x_2 = 2 \in [0;\infty]\\\) ta được \\\(y_2 = f(x_2) = 2^2 = 4 \in \mathbb{R}\\\)

Vì \\\(x_1 \ne x_2\\\) \\\((1 \ne 2)\\\) kéo theo \\\(f(x_1) \ne f(x_2)\\\) \\\((1 \ne 4)\\\) nên \\\(f: [0;\infty] \to \mathbb{R}, x \to x^2\\\) là ***đơn ánh***.

Với \\\(y = -1\\\), \\\(\nexists x \in [0;\infty]\\\) sao cho \\\(x^2 = -1\\\). Vậy nên \\\(f: [0;\infty] \to \mathbb{R}, x \to x^2\\\)  không là ***toàn ánh***.

Vì ánh xạ \\\(f: [0;\infty] \to \mathbb{R}, x \to x^2\\\)  chỉ là **đơn ánh** mà không phải là **toàn ánh**, nên ánh xạ này không phải là ***song ánh***.

**Ví dụ 2.5**: Cho \\\(f: \mathbb{R} \to [0; \infty], x \mapsto x^2\\\)

Với \\\(x_1 = -1 \in \mathbb{R}\\\) ta được \\\(y_1 = f(x_1) = (-1)^2 = 1 \in [0;\infty]\\\)

Với \\\(x_2 = \sqrt{2} \in \mathbb{R}\\\) ta được \\\(y_2 = f(x_2) = (\sqrt{2})^2 = 2 \in [0;\infty]\\\)

Vậy \\\(\exists x \in \mathbb{R}\\\) để \\\(y = f(x) = x^2\\\), nên \\\(f: \mathbb{R} \to [0; \infty], x \mapsto x^2\\\) là ***toàn ánh***.

Với \\\(x_3 = 1 \in \mathbb{R}\\\) ta được \\\(y_3 = f(x_3) = 1^2 = 1 \in [0;\infty]\\\) 

Vì \\\(x_1 \ne x_3\\\) \\\((-1 \ne 1)\\\) mà kéo theo \\\(f(x_1) = f(x_3)\\\), nên \\\(f: \mathbb{R} \to [0; \infty], x \mapsto x^2\\\) không là ***đơn ánh***.

Vì ánh xạ \\\(f: \mathbb{R} \to [0;\infty], x \to x^2\\\)  chỉ là **toàn ánh** mà không phải là **đơn ánh**, nên ánh xạ này không phải là ***song ánh***.

**Ví dụ 2.6**: Cho \\\(f: [0;\infty] \to [0;\infty], x \to x^2\\\)

Với \\\(x_1 = 1 \in [0;\infty]\\\) ta được \\\(y_1 = f(x_1) = 1^2 = 1 \in [0;\infty]\\\)

Với \\\(x_2 = 2 \in [0;\infty]\\\) ta được  \\\(y_2 = f(x_2) = 2^2 =4 \in [0;\infty]\\\)

Vì \\\(x_1 \ne x_2\\\) \\\((1 \ne 2)\\\) kéo theo \\\(f(x_1) \ne f(x_2)\\\) \\\((1 \ne 4)\\\) nên \\\(f: [0;\infty] \to \[0;\infty], x \to x^2\\\) là ***đơn ánh***.

Hơn nữa, \\\(\exists x \in [0;\infty]\\\) để \\\(y = f(x) = x^2\\\), nên \\\(f: [0;\infty] \to [0; \infty], x \mapsto x^2\\\) là ***toàn ánh***.

Vì ánh xạ \\\(f: [0;\infty] \to [0;\infty], x \to x^2\\\) vừa là **đơn ánh** và cũng là vừa **toàn ánh** nên ánh xạ này là ***song ánh***.

*** 

## 3. Số phức 

**Định nghĩa 3.1**: 

\\\(
   \begin{theorem}
      Số phức là một biểu thức có dạng 
      $$z = a +bi$$
      trong đó \\\(a, b \in \mathbb{R}\\\), và \\\(i \\\) là một kí hiệu gọi là đơn vị ảo.
   \end{theorem}
   \\\)


*** 

## 4. Ma trận 

. . . 

*** 

## 5. Phép thế và dấu của phép thế

**Định nghĩa 5.1 (phép thế)**: 

> Cho n là một số nguyên dương. Mỗi song ánh từ tập hợp \\\(X\\\) = {1, 2, \\\(\dots\\\), n} vào chính nó được gọi là một phép thế cấp n. 

Một phép thế cấp n còn được gọi là một phép thế bậc n hoặc là một hoán vị bậc n.

Phép thế được kí hiệu bởi chữ cái Hy Lạp: \\\(\sigma\\\), \\\(\tau\\\), ...

Tập hợp các phép cấp n được kí hiệu là \\\(S_n\\\). Số các phép cấp n là \\\(n!\\\). 

Một phép thế \\\(\sigma\\\) cấp n được biểu diễn dưới dạng một bằng gồm hai dòng: 

$$\sigma = \begin{pmatrix}
1 & 2 & \ldots & n\\
\sigma(1) & \sigma(2) & \ldots & \sigma(n)\\
\end{pmatrix}
$$

**Ví dụ 5.2**: Cho một ma trận vuông cỡ 2 \\\(\times\\\) 2. Ma trận vuông 2 \\\(\times\\\) 2 này có 2! = 2 phép thế cấp 2, đó là 

\\\(\sigma(1) = \\\)
\\\(
\begin{pmatrix}
   1 & 2 \\
   1 & 2
\end{pmatrix} 
\\\)

\\\(\sigma(2) = \\\)
\\\(
\begin{pmatrix}
   1 & 2 \\
   2 & 1
\end{pmatrix} 
\\\)

**Định nghĩa 5.3 (dấu phép thế)**:   

> Cho \\\(\sigma \in S_n\\\). Dấu của \\\(\sigma\\\), kí hiệu là \\\(sgn(\sigma)\\\), được xác định bởi:

$$
\begin{equation}
\begin{aligned}
\operatorname{sgn}(\sigma) = \prod_{1 \le i < j \le n} \frac{\sigma(j) - \sigma(i)}{j - i} \in \{\pm 1\}
\end{aligned}
\end{equation}
$$

Phép thế \\\(\sigma\\\) được gọi là phép thế ***chẵn*** nếu \\\(sgn(\sigma) = 1\\\). Nếu \\\(sgn(\sigma) = -1\\\) thì phép thế \\\(\sigma\\\) được gọi là phép thế ***lẻ***. 

**Ví dụ 5.4**: Cho một phép thế cấp 6 sau: 

$$\sigma = \begin{pmatrix}
   1 & 2 & 3 & 4 & 5 & 6\\
   5 & 1 & 4 & 2 & 3 & 6
\end{pmatrix}$$


Phép thế này là phép thế chẵn hay phép thế lẻ ? 

Bằng cách áp dụng công thức dấu của phép thế từ **định nghĩa 5.3** trên ta được: 

$$
\operatorname{sgn}(\sigma) = \prod_{1 \le i < j \le 6} \frac{\sigma(j) - \sigma(i)}{j - i} 
= \left( \frac{1-5}{2-1} . \frac{4-5}{3-1} . \frac{2-5}{4-1} . \frac{3-5}{5-1} . \frac{6-5}{6-1} \right) . \left (\frac{4-1}{3-2} . \frac{4-2}{4-2} . \frac{3-1}{5-2} . \frac{6-1}{6-2} \right) . \left( \frac{2-4}{4-3} . \frac{3-4}{5-3} . \frac{6-4}{6-3} \right) . \left(\frac{3-2}{5-4}. \frac{6-2}{6-4}\right) . \left( \frac{6-3}{6-5}\right)
= 1
$$

Vì dấu của phép thế \\\(\sigma\\\), \\\(sgn(\sigma) = 1\\\), nên đây là phép thế ***chẵn***. 

Từ **định nghĩa 5.3** về dấu của phép thế trên, ta có một cách khác để tính dấu của phép thế. Nhưng trước tiên ta cần tìm hiểu về ***nghịch thế***.

**Định nghĩa 5.5**: Cho \\\(f: X \to X\\\) là phép thế cấp n, với \\\(X\\\) = {1, 2, ..., n}: 

> (i) Cặp \\\((\sigma(i), \sigma(j))\\\) với \\\(1 \le i < j \le n\\\) được gọi là nghịch thế nếu \\\(\sigma(i) > \sigma(j)\\\)

> (ii) Nếu cặp \\\((\sigma(i), \sigma(j))\\\) có số lượng nghịch thế là chẵn, thì phép thế \\\(\sigma\\\) được gọi là phép thế ***chẵn*** và ta có được dấu phép thế \\\(sgn(\sigma) = 1\\\). Còn nếu cặp \\\((\sigma(i), \sigma(j))\\\) có số lượng nghịch thế là lẻ, thì phép thế \\\(\sigma\\\) được gọi là phép thế ***lẻ*** ta có được dấu phép thế \\\(sgn(\sigma) = -1\\\). 

Áp dụng **định nghĩa 5.5** vào lại **ví dụ 5.4** trên ta được: 

\\\((\sigma(i), \sigma(j))\\\) = {(5,4);(5,1);(5,2); (5,3); (4,2); (4,3)}

Vì cặp \\\((\sigma(i), \sigma(j))\\\) có số lượng nghịch thế là chẵn, nên theo **(ii)** của **định nghĩa 5.5**, phép thế \\\(\sigma\\\) là phép thế chẵn, có dấu của phép thế \\\(sgn(\sigma) = 1\\\).

## 6. Định thức

**Định nghĩa 6.1**: 

> Giả sử \\\(A = (a_{ij})_{n \times n}\\\) là một ma trận vuông cấp \\\(n\\\) với các phần tử là số thực hoặc số phức. Định thức của ma trận \\\(A\\\), ký hiệu là \\\(\det(A)\\\) được cho bởi:

$$
\begin{equation}
\begin{aligned}
\det(A) = \sum_{\sigma \in S_n} \operatorname{sgn}(\sigma) \prod_{k=1}^{n} a_{k\sigma(k)}
\end{aligned}
\end{equation}
$$

trong đó tổng ở vế phải được lấy trên tập \\\(S_n\\\) tất cả các phép thế \\\(\sigma\\\) cấp n.

***

## 7. Khai triển Laplace

. . .

***

## 8. Hạng của ma trận

. . . 

***

## 9. Hệ phương trình tuyến tính

. . .

