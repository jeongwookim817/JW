
# 문제 풀이: 상태 공간 모델 및 전달 함수

## P3.1 문제: 스프링-질량-댐퍼 시스템
그림 P3.1에 주어진 스프링-질량-댐퍼 시스템에 대해 다음을 해결합니다.

### (a) 적절한 상태 변수를 설정하라.
시스템의 상태 변수를 질량의 변위와 속도로 정의합니다.
- \(x_1(t) = y(t)\): 질량의 변위
- \(x_2(t) = \dot{y}(t)\): 질량의 속도

### (b) 상태 변수의 1차 미분 방정식을 구하라.
뉴턴의 제2법칙에 따라 시스템의 운동 방정식은 다음과 같습니다:
\[
M\ddot{y}(t) + b\dot{y}(t) + ky(t) = F(t)
\]
이를 상태 변수로 표현하면:
\[
\dot{x}_1(t) = x_2(t)
\]
\[
M\dot{x}_2(t) = -kx_1(t) - bx_2(t) + F(t)
\]
즉, 상태 방정식은 다음과 같이 표현됩니다:
\[
\dot{x}(t) = 
egin{bmatrix}
0 & 1 \
-rac{k}{M} & -rac{b}{M}
\end{bmatrix}
x(t) +
egin{bmatrix}
0 \
rac{1}{M}
\end{bmatrix}
F(t)
\]

### (c) 상태 미분 방정식을 작성하라.
상태 미분 방정식은 위에서 구한 1차 미분 방정식으로부터 다음과 같이 정의됩니다:
\[
\dot{x}(t) = Ax(t) + Bu(t)
\]
여기서:
\[
A = 
egin{bmatrix}
0 & 1 \
-rac{k}{M} & -rac{b}{M}
\end{bmatrix}, \quad B = 
egin{bmatrix}
0 \
rac{1}{M}
\end{bmatrix}
\]
출력은 변위 \(y(t)\)이므로:
\[
y(t) = [1 \quad 0]x(t)
\]
따라서 출력 행렬 \(C\)와 전달 행렬 \(D\)는:
\[
C = [1 \quad 0], \quad D = 0
\]

## P3.3 문제: RLC 회로
주어진 RLC 네트워크에 대해 상태 방정식을 구합니다.

### (a) 상태 변수 설정
상태 변수는 다음과 같이 정의됩니다:
- \(x_1(t) = i_L(t)\): 인덕터 전류
- \(x_2(t) = v_C(t)\): 커패시터 전압

### (b) 상태 미분 방정식 구하기
회로에서 KVL 및 KCL을 사용하여 다음의 방정식을 얻습니다:
\[
Lrac{di_L(t)}{dt} + v_C(t) = v_1(t)
\]
\[
Crac{dv_C(t)}{dt} + rac{v_C(t)}{R} = i_L(t)
\]
이를 상태 방정식으로 변환하면:
\[
\dot{x}_1(t) = rac{1}{L}(v_1(t) - x_2(t))
\]
\[
\dot{x}_2(t) = -rac{1}{RC}x_2(t) + rac{1}{C}x_1(t)
\]
즉, 상태 방정식은 다음과 같습니다:
\[
\dot{x}(t) = 
egin{bmatrix}
0 & rac{1}{L} \
-rac{1}{C} & -rac{1}{RC}
\end{bmatrix}
x(t) + 
egin{bmatrix}
rac{1}{L} \
0
\end{bmatrix}
v_1(t)
\]
출력은 커패시터 전압이므로:
\[
y(t) = 
egin{bmatrix}
0 & 1
\end{bmatrix}
x(t)
\]

## P3.5 문제: 폐루프 제어 시스템
그림 P3.5에 주어진 폐루프 시스템에 대해 전달 함수를 구합니다.

### (a) 폐루프 전달 함수 구하기
폐루프 전달 함수는 다음과 같습니다:
\[
T(s) = rac{Y(s)}{R(s)} = rac{G(s)H(s)}{1 + G(s)H(s)}
\]
여기서 \(G(s) = rac{s + 2}{s + 8}\)이고, \(H(s) = rac{1}{s - 3}\)입니다. 따라서:
\[
T(s) = rac{rac{s + 2}{s + 8} \cdot rac{1}{s - 3}}{1 + rac{s + 2}{s + 8} \cdot rac{1}{s - 3}} = rac{(s + 2)}{(s + 8)(s - 3) + (s + 2)}
\]

### (b) 상태 변수 모델 구하기
시스템의 상태 공간 표현을 위해 다음과 같이 정의합니다:
- 상태 변수 \(x_1 = v_1(t)\): 제어 신호
- 상태 변수 \(x_2 = v(t)\): 속도

상태 방정식은:
\[
\dot{x}_1(t) = -8x_1(t) + r(t)
\]
\[
\dot{x}_2(t) = -3x_2(t) + x_1(t)
\]
출력은 \(y(t) = x_2(t)\)이므로 상태 공간 표현은 다음과 같습니다:
\[
\dot{x}(t) = 
egin{bmatrix}
-8 & 0 \
1 & -3
\end{bmatrix}
x(t) + 
egin{bmatrix}
1 \
0
\end{bmatrix}
r(t)
\]
출력 방정식은:
\[
y(t) = 
egin{bmatrix}
0 & 1
\end{bmatrix}
x(t)
\]

## P3.12 문제: 상태 변수 모델과 상태 전이 행렬
시스템의 전달 함수는 다음과 같습니다:
\[
T(s) = rac{8(s + 5)}{s^3 + 12s^2 + 44s + 48}
\]

### (a) 상태 변수 모델 구하기
전달 함수를 상태 공간 표현으로 변환하면:
\[
\dot{x}(t) = 
egin{bmatrix}
0 & 1 & 0 \
0 & 0 & 1 \
-48 & -44 & -12
\end{bmatrix}
x(t) + 
egin{bmatrix}
0 \
0 \
8
\end{bmatrix}
r(t)
\]
출력 방정식은:
\[
y(t) = 
egin{bmatrix}
5 & 0 & 0
\end{bmatrix}
x(t)
\]

### (b) 상태 전이 행렬 \(\Phi(t)\) 구하기
상태 전이 행렬은 다음 미분 방정식을 만족하는 행렬 함수입니다:
\[
rac{d\Phi(t)}{dt} = A\Phi(t), \quad \Phi(0) = I
\]
따라서 상태 전이 행렬은 시스템의 행렬 \(A\)의 지수 함수로 표현됩니다:
\[
\Phi(t) = e^{At}
\]

## P3.17 문제: 상태 변수 표현으로부터 전달 함수 구하기
시스템의 상태 변수 방정식은 다음과 같습니다:
\[
\dot{x}(t) = 
egin{bmatrix}
1 & 1 & -1 \
4 & 3 & 0 \
-2 & 1 & 10
\end{bmatrix}
x(t) + 
egin{bmatrix}
0 \
0 \
4
\end{bmatrix}
u(t)
\]
출력 방정식은:
\[
y(t) = 
egin{bmatrix}
1 & 0 & 0
\end{bmatrix}
x(t)
\]

시스템의 전달 함수는 다음과 같이 계산됩니다:
\[
G(s) = C(sI - A)^{-1}B + D
\]
여기서 \(A\), \(B\), \(C\)는 위에서 정의된 행렬입니다.
