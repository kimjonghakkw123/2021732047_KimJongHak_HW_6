# 3장 과제 풀이 (P3.1, P3.3, P3.5, P3.12, P3.17)

**학번:** 2021732047  
**이름:** 김종학

---

## P3.1

**문제:**  
아래의 미분방정식을 상태방정식(phase variable form)으로 변환하시오.

$$
\ddot{y}(t) + a_1 \dot{y}(t) + a_0 y(t) = b_0 u(t)
$$

**풀이:**  

$$
\begin{aligned}
\dot{x}_1 &= x_2 \\
\dot{x}_2 &= -a_1 x_2 - a_0 x_1 + b_0 u \\
y &= x_1
\end{aligned}
$$

---

## P3.3

**문제:**  
아래의 미분방정식을 상태방정식(phase variable form)으로 변환하시오.

$$
\dddot{y}(t) + a_2 \ddot{y}(t) + a_1 \dot{y}(t) + a_0 y(t) = b_0 u(t)
$$

**풀이:**  

$$
\begin{aligned}
\dot{x}_1 &= x_2 \\
\dot{x}_2 &= x_3 \\
\dot{x}_3 &= -a_2 x_3 - a_1 x_2 - a_0 x_1 + b_0 u \\
y &= x_1
\end{aligned}
$$

---

## P3.5

**문제:**  
아래의 미분방정식을 상태방정식(phase variable form)으로 변환하시오.

$$
\ddot{y}(t) + 3\dot{y}(t) + 2y(t) = 4u(t)
$$

**풀이:**  

$$
\begin{aligned}
\dot{x}_1 &= x_2 \\
\dot{x}_2 &= -3x_2 - 2x_1 + 4u \\
y &= x_1
\end{aligned}
$$

---

## P3.12

**문제:**  
아래의 미분방정식을 상태방정식(phase variable form)으로 변환하시오.

$$
\dddot{y}(t) + 6\ddot{y}(t) + 11\dot{y}(t) + 6y(t) = 2u(t)
$$

**풀이:**  

$$
\begin{aligned}
\dot{x}_1 &= x_2 \\
\dot{x}_2 &= x_3 \\
\dot{x}_3 &= -6x_3 - 11x_2 - 6x_1 + 2u \\
y &= x_1
\end{aligned}
$$

---

## P3.17

**문제:**  
아래의 미분방정식을 상태방정식(phase variable form)으로 변환하시오.

$$
\ddot{y}(t) + 5\dot{y}(t) + 6y(t) = 3u(t)
$$

**풀이:**  

$$
\begin{aligned}
\dot{x}_1 &= x_2 \\
\dot{x}_2 &= -5x_2 - 6x_1 + 3u \\
y &= x_1
\end{aligned}
$$
