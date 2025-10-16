# 2021732047_KimJongHak_HW_61
## P3.1

그림 P3.1에 스프링-질량-감쇠기 시스템이 주어져 있다.  

(a) 적당한 상태변수를 설정하라.  
(b) 상태변수로 표현된 1차 미분방정식을 구하라.  
(c) 상태미분방정식을 구하라.

<p align="center">
  <img width="334" height="149" alt="image" src="https://github.com/user-attachments/assets/bfc8bd23-9fa9-4717-b31b-c7c1c3cc838a" />
</p>


### (a) 적당한 상태변수 설정


#### 미분방정식 만들기

$$
F(t) = M \frac{d^2 y(t)}{dt^2} + b \frac{d y(t)}{dt} + ky(t)
$$

이때 서로 미분(또는 적분) 관계인 

$$
y(t), \frac{d y(t)}{dt} 
$$

를 상태변수로 설정한다

$$
x_1(t) = y(t), \quad x_2(t) = \dot{y}(t) = \frac{d y(t)}{dt}
$$

따라서,

$$
y(t) = x_1(t)
$$

$$
\frac{d y(t)}{dt} = x_2(t) = \frac{d x_1(t)}{dt}
$$

$$
\frac{d^2 y(t)}{dt^2} = \frac{d x_2(t)}{dt}
$$

---

### (b) 상태변수로 표현된 1차 미분방정식

첫 번째 방정식:

$$
\dot{x}_1(t) = x_2(t)
$$

두 번째 방정식:

$$
\dot{x}_2(t) = - \frac{b}{M} x_2(t) -\frac{k}{M} x_1(t)  + \frac{F(t)}{M}
$$

---

### (c) 상태미분방정식

State space equation은 State differential equation과 Output equation으로 나눌 수 있다.

$$
\mathbf{\dot{X}} = A\mathbf{\{x(t)}} + B \mathbf{\{u(t)}}
$$

와

$$
y(t) = x_1(t) = C x(t) + D u(t)
$$

$$
\begin{bmatrix}
\dot{x}_1\\
\dot{x}_2
\end{bmatrix} =
\begin{bmatrix}
0 & 1 \\
-\frac{k}{M} & -\frac{b}{M}
\end{bmatrix}
\begin{bmatrix}
x_1 \\
x_2
\end{bmatrix}
+
\begin{bmatrix}
0 \\
\frac{1}{M}
\end{bmatrix}F(t)
$$

즉, State differential equation은

<p align="center">
$$
\mathbf{\dot{X}} =
\begin{bmatrix}
0 & 1 \\
-\frac{k}{M} & -\frac{b}{M}
\end{bmatrix}
\mathbf{x}
+
\begin{bmatrix}
0 \\
\frac{1}{M}
\end{bmatrix} F(t)
$$
</p>
이고

Output equation은

$$
y(t) = [1\ 0]\ \mathbf{x}(t)
$$

이다.


---
## P3.3

그림 P3.3과 같은 RLC 회로가 주어졌다. 상태변수  
$(x_1(t) = i_L(t) ), ( x_2(t) = v_C(t))$ 로 설정하고 상태미분방정식을 구하라.

부분해답답:

$$
A =
\begin{bmatrix}
0 & \dfrac{1}{L} \\
-\dfrac{1}{C} & -\dfrac{1}{RC}
\end{bmatrix}
$$

<p align="center">
 <img width="1202" height="1000" alt="image" src="https://github.com/user-attachments/assets/03cecd7f-8639-4412-a4cc-53e13c3a4110" />
</p>

## 상태방정식 유도 (RLC 회로)

### 상태변수

$$
x_1(t) = i_L(t), \quad x_2(t) = v_C(t)
$$

---

### 1 : KCL 적용

$$
x_1(t) = \frac{v_2(t) - x_2(t)}{R} - C \frac{d x_2(t)}{dt} 
$$

---

### 2 : KVL 적용

$$
-v_1(t) + L \frac{d x_1(t)}{dt} + v_2(t) - x_2(t) = 0
$$

---

### 3 상태변수로 표현한 1차 미분방정식

$$
\begin{aligned}
\dot{x}_1(t) &= \frac{1}{L}V_1(t) - \frac{1}{L}V_2(t) + \frac{1}{L}x_2(t) \\
\dot{x}_2(t) &= -\frac{1}{C}x_1(t) + \frac{V_2(t)}{RC} - \frac{x_2(t)}{RC}
\end{aligned}
$$

$$
v_p(t) = y(t) = v_2(t) - v_c(t) = v_2(t) - x_2(t)
$$


---

### 4 상태미분방정식

$$
\dot{\mathbf{X}}(t) =
\begin{bmatrix}
  0 & \frac{1}{L} \\
  -\frac{1}{C} & -\frac{1}{RC}
\end{bmatrix}
\begin{bmatrix}
  x_1 \\
  x_2
\end{bmatrix}
+
\begin{bmatrix}
  \frac{1}{L} & -\frac{1}{L} \\
  0 & \frac{1}{RC}
\end{bmatrix}
\begin{bmatrix}
  V_1 \\
  V_2
\end{bmatrix}
$$

여기서

$$
\mathbf{u}(t) =
\begin{bmatrix}
V_1(t) \\
V_2(t)
\end{bmatrix}
$$

이므로

$$
\dot{\mathbf{x}}(t) =
\begin{bmatrix}
0 & \frac{1}{L} \\
-\frac{1}{C} & -\frac{1}{RC}
\end{bmatrix}
\mathbf{X}(t)
+
\begin{bmatrix}
\frac{1}{L} & -\frac{1}{L} \\
0 & \frac{1}{RC}
\end{bmatrix}
\mathbf{u}(t)
$$

로 표현할 수 있다. 즉 위의 식이 state differential equation 이다.

$$
y(t) =
\begin{bmatrix}
0 & -1
\end{bmatrix}
\mathbf{X}(t)
+
\begin{bmatrix}
0 & 1
\end{bmatrix}
\mathbf{u}(t)
$$

위의 식이 임의로 output를 지정한 Output equation이다.

---

## P3.5

그림 P3.5에 폐루프 제어시스템이 주어져 있다.  
(a) 폐루프 전달함수 $( T(s) = \dfrac{Y(s)}{R(s)} )$를 구하라.  
(b) 상태변수 모델을 구하고 위상변수형 블록선도를 작성하라. (위상변수형 블럭선도는 구하지 않겠다.)

<p align="center">
 <img width="541" height="249" alt="image" src="https://github.com/user-attachments/assets/c8a00e52-e277-4600-9ad6-018d62bfb428" />

</p>



### (a) 폐루프 전달함수 T(s) 구하기

개루프 전달함수 T(s)_o는

$$
T(s)_o = \frac{s+2}{s+8} \cdot \frac{1}{s-3} \cdot \frac{1}{5}
$$

이다. 피드백은 단위피드백이므로 이를 수식으로 표현하면

$$
\frac{T(s)_o}{1 + T(s)_o} =
\frac{s+2}{(s+8)(s-3)s + (s+2)s} =
\frac{s+2}{s^3 + 5s^2 - 23s + 2}
$$

따라서, 폐루프 전달함수 T(s)는 다음과 같다

$$
T(s)=\frac{s+2}{s^3 + 5s^2 - 23s + 2}
$$


---


### (b) 상태변수 모델 구하기


$$
T(s) = \frac{Y(s)}{R(s)} \cdot \frac{Z(s)}{Z(s)}
$$

로 표현 가능하다.


따라서

$$
Y(s) = s Z(s) + 2 Z(s)
$$

$$
R(s) = s^3 Z(s) + 5s^2 Z(s) - 23s Z(s) + 2\ Z(s)
$$

이고, 역라플라스를 취해주면 

$$
y(t)= \dot{z}(t) + 2 z(t) 
$$

$$
r(t)=\dddot{z}(t) + 5\ddot{z}(t) - 23\dot{z}(t) + 2 z(t) 
$$

$$
\dddot{z}(t) = r(t) - 5\ddot{z}(t) + 23\dot{z}(t) - 2 z(t) 
$$

이때 상태변수를 다음과 같이 지정한다.

$$
x_1(t) = z(t), \quad x_2(t) = \dot{z}(t), \quad x_3(t) = \ddot{z}(t)
$$

이 상태변수를 이용해 1차미분방정식과 출력 방정식을 구하면

$$
\begin{aligned}
\dot{x}_1(t) &= x_2(t) \\
\dot{x}_2(t) &= x_3(t) \\
\dot{x}_3(t) &= -5x_3(t) + 23x_2(t) - 2x_1(t) + r(t)
\end{aligned}
$$

$$
y(t) = 2x_1(t) + x_2(t)
$$

과 같다.

---

이때 상태 미분방정식은

$$
\dot{X}(t) =
\begin{bmatrix}
0 & 1 & 0 \\
0 & 0 & 1 \\
-2 & 23 & -5
\end{bmatrix}
X(t)
+
\begin{bmatrix}
0 \\
0 \\
1
\end{bmatrix}
r(t)
$$

이고,

출력 방정식은

$$
y(t) =
\begin{bmatrix}
2 & 1 & 0
\end{bmatrix}
X(t)
$$

이다.


---

## P3.12

<p align="center">
  <img width="497" height="185" alt="image" src="https://github.com/user-attachments/assets/6907a2bf-1e90-4619-bc27-c11d699837eb" />
</p>

(a) 상태공간모델을 구하라.  
(b) 상태천이행렬 $\Phi(t)$를 구하라.

---

### (a) 상태공간모델 구하기

우선 전달함수는 다음과 같이 표현 가능하다. 

$$
T(s) = \frac{8(s + 5)Z(s)}{(s^3 + 12s^2 + 44s + 48)Z(s)}
$$

따라서

$$
Y(s) = 8 (s + 5) Z(s) = 8s Z(s) + 40 Z(s)
$$

$$
R(s) = (s^3 + 12s^2 + 44s + 48) Z(s) = s^3 Z(s) + 12s^2 Z(s) + 44s Z(s) + 48 Z(s)
$$

이다.

Y(s), R(s)를 역라플라스 변환을 취해주면

$$
y(t) = 8 \dot{z}(t) + 40 z(t)
$$

$$
r(t) = \dddot{z}(t) + 12 \ddot{z}(t) + 44 \dot{z}(t) + 48 z(t)
$$

이고, 추가로

$$
\dddot{z}(t) = 12 \ddot{z}(t) - 44 \dot{z}(t) - 48 z(t) + r(t)
$$

를 구할 수 있다.

---

이때, 상태변수를 아래와 같이 지정한다.

$$
x_1(t) = z(t), \quad x_2(t) = \dot{z}(t), \quad x_3(t) = \ddot{z}(t)
$$

따라서,

$$
\dot{x}_1(t) = x_2(t)
$$

$$
\dot{x}_2(t) = x_3(t)
$$

$$
\dot{x}_3(t) = -48 x_1(t) - 44 x_2(t) - 12 x_3(t) + r(t)
$$

인 상태미분방정식과 

$$
y(t) = 40 x_1(t) + 8 x_2(t)
$$

인 출력방정식을 구할 수 있다.

---

이를 활용해 상태공간방정식을 구하면

$$
\dot{\mathbf{x}}(t) =
\begin{bmatrix}
0 & 1 & 0 \\
0 & 0 & 1 \\
-48 & -44 & -12
\end{bmatrix}
\mathbf{x}(t)
+
\begin{bmatrix}
0 \\
0 \\
1
\end{bmatrix}
r(t)
$$

$$
y(t) =
\begin{bmatrix}
40 & 8 & 0
\end{bmatrix}
\mathbf{x}(t)
$$

이다.

행렬방정식의 해의 형태는 다음과 같다.

$$
\dot{X}(t) = A X(t) + B R(t)
$$

$$
Y(t) = C X(t) + D R(t)
$$

여기서,

$$
A =
\begin{bmatrix}
0 & 1 & 0 \\
0 & 0 & 1 \\
-48 & -44 & -12
\end{bmatrix},
\quad
B =
\begin{bmatrix}
0 \\
0 \\
1
\end{bmatrix},
\quad
C =
\begin{bmatrix}
40 & 8 & 0
\end{bmatrix},
\quad
D = [0]
$$

으로 A, B, C, D 행렬의 값을 알 수 있다.

---

### (b) 상태천이행렬 $\Phi(t)$ 구하기

상태천이행렬은 다음과 같다.

$$
\Phi(s) = (sI - A)^{-1}
$$

이때 

$\Phi(s) = (sI - A)^{-1}=\frac{\text{adj}(sI - A)}{|sI - A|}$

이다.

우선,

$$
sI - A =
\begin{bmatrix}
s & -1 & 0 \\
0 & s & -1 \\
48 & 44 & s + 12
\end{bmatrix}
$$

행렬식은 다음과 같다:

$$
|sI - A| = s^3 + 12 s^2 + 44 s + 48
$$

여기서 adj(sI-A)는

$$
\begin{bmatrix}
s^2 + 12s + 44 & s + 12 & 1 \\
-48 & s^2 + 12s & s \\
-48s & -44s -48 & s^2
\end{bmatrix}
$$

따라서 상태천이행렬은 다음과 같다:

$$
\Phi(s) = \frac{1}{s^3 + 12 s^2 + 44 s + 48}
\begin{bmatrix}
s^2 + 12s + 44 & s + 12 & 1 \\
-48 & s^2 & s \\
-48 & -48 & s^2
\end{bmatrix}
$$
 
이때 천이행렬의 역라플라스 변환을 통해 $\Phi(t)$를 구할 수 있다.


$$
\Phi(t) =
\begin{bmatrix}
3e^{-2t} - 3e^{-4t} + e^{-6t} & \dfrac{5}{4}e^{-2t} - 2e^{-4t} + \dfrac{3}{4}e^{-6t} & \dfrac{1}{8}e^{-2t} - \dfrac{1}{4}e^{-4t} + \dfrac{1}{8}e^{-6t} \\
-6e^{-2t} + 12e^{-4t} - 6e^{-6t} & -\dfrac{5}{2}e^{-2t} + 8e^{-4t} - \dfrac{9}{2}e^{-6t} & -\dfrac{1}{4}e^{-2t} + e^{-4t} - \dfrac{3}{4}e^{-6t} \\
12e^{-2t} - 48e^{-4t} + 36e^{-6t} & 5e^{-2t} - 32e^{-4t} + 27e^{-6t} & \dfrac{1}{2}e^{-2t} - 4e^{-4t} + \dfrac{9}{2}e^{-6t}
\end{bmatrix}
$$

이다.

---

## P3.17

다음과 같은 상태변수 방정식으로 표현된 시스템이 있다.

<p align="center">
  <img width="1919" height="999" alt="image" src="https://github.com/user-attachments/assets/0d732764-ecc3-419a-a557-02f0143b6e52" />
</p>

$$
G(s) = \frac{Y(s)}{U(s)} \text{ 를 구하라.}
$$

---


주어진 상태변수 방정식을 라플라스 변환 하면


$$
s\mathbf{X}(s) =
\begin{bmatrix}
1 & 1 & -1 \\
4 & 3 & 0 \\
-2 & 1 & 0
\end{bmatrix}
\mathbf{X}(s)
+
\begin{bmatrix}
0 \\
0 \\
4
\end{bmatrix}
u(s)
$$

$$
\mathbf{Y}(s) =
\begin{bmatrix}
1 & 0 & 0
\end{bmatrix}
\mathbf{X}(s)
$$

이고, 행렬 A, B, C, D는

$$
A =
\begin{bmatrix}
1 & 1 & -1 \\
4 & 3 & 0 \\
-2 & 1 & 0
\end{bmatrix}
$$

$$
B =
\begin{bmatrix}
0 \\
0 \\
4
\end{bmatrix}
$$

$$
C =
\begin{bmatrix}
1 & 0 & 0
\end{bmatrix}
$$

$$
D = 0
$$

이다.



$$
\left[ sI - A \right] \mathbf{X}(s) = \mathbf{B}U(s)
$$

$$
\mathbf{X}(s) = \left[ sI - A \right]^{-1} \mathbf{B}U(s) = \Phi(s)\mathbf{B}U(s)
$$

D = 0 이므로 생략하였다.
위의 식에 의해 Y(s)와 U(s)에 대한 식을 얻어 대입하면,

$$
G(s) = \frac{\mathbf{Y}(s)}{U(s)}
= \frac{C\ \mathbf{X}(s)}{\mathbf{X}(s)}\ \{\Phi(s)\mathbf{B}}
= \ C\ \Phi(s)\mathbf{B} \
$$

이다.


---

이때, $\Phi(s)$ 는

$$
(sI - A)^{-1}=\frac{\text{adj}(sI - A)}{|sI - A|}
$$

이므로

$$
|sI - A| = s^3 - 14 s^2 + 37 s + 20
$$

이고,

여기서 adj(sI-A)는

$$
\begin{bmatrix}
(s - 3)(s - 10) & s - 11 & -s + 3 \\
4s - 40 & s^2 - 11s + 8 & -4 \\
-2s + 10 & s - 3 & s^2 -4s -1
\end{bmatrix}
$$

이다.

따라서 상태천이행렬 $\Phi(s)$ 는 

$$
\Phi(s) =
\frac{1}{s^3 - 14s^2 + 37s + 20}
\begin{bmatrix}
s^2 - 13s + 30 & s - 11 & -s + 3 \\
4s - 40 & s^2 - 11s + 8 & -4 \\
-2s + 10 & s - 3 & s^2 - 4s - 1
\end{bmatrix}
$$

이다.

---


전달함수 G(s)는 아래의 수식을 따른다.

$$
G(s) = C \Phi(s) B + D
$$

여기서  

$$
C =
\begin{bmatrix}
1 & 0 & 0
\end{bmatrix}
$$ 

$$
B =
\begin{bmatrix}
0 \\
0 \\
4
\end{bmatrix}
$$

$$
D = 0
$$

이므로, 이를 계산하면

$$
G(s) = \frac{-4s + 12}{s^3 - 14s^2 + 37s + 20}
$$
