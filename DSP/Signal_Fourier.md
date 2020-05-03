# 디지털 신호 처리(DSP : Digital Signal Processing)
#### 디지털화된 신호를 원하는 방향으로 정보 신호를 수정하거나 개선할 목적으로 알고리즘에 의해 수치적으로 처리하는 것을 말함.

## 신호(Signal)
정보를 갖는 것은 모두 신호로 볼 수 있음(정보통신기술용어해설 - 참고.).
- 어떤 현상을 시간, 공간에 따라 변화하는 물리량으로 표시한 '함수'
* 주로, '시간'과 관련된 물리량의 수학적 표현을 일컬음

1. 시간

        연속적 연속시간 신호(Continuous Time Signal)
        이산적 이산시간 신호(Discrete Time Signal)

2. 크기

        연속적 연속크기 신호(Continuous Amplitude Signal)
        이산적 이산크기 신호(Discrete Amplitude Signal)

연속과 이산 신호 그래프

<p align="center"><img src="https://user-images.githubusercontent.com/45933225/80908943-14e23500-8d5f-11ea-9ced-d208ef4fac8b.png" width="75%"></p>

아날로그 신호(Analog Signal) - 연속시간 신호이면서 동시에 연속크기 신호
디지털 신호(Digital Signal) - 이산시간 신호이면서 동시에 이산크기 신호

아날로그 -> 디지털 신호 변환 과정(시간, 크기)

    1. 샘플링(Sampling) - 시간이 연속적이며 크기가 연속인 신호 시간을 이산으로 변환
    2. 양자화(Quantization) - 시간이 이산이며 크기가 연속인 신호 크기를 이산으로 변환

*무리수는 컴퓨터로 정확히 표현할 수 없어 특정한 값으로 양자화하므로 오차가 발생함.

## 푸리에 변환(FT : Fourier Transform)
시간에 대한 함수 (혹은 신호) 를 함수를 구성하고 있는 주파수 성분으로 분해하는 작업하는 것을 말함.
따라서 무한히 어떤 항을 더함으로써 주기를 얻을 수 있음.
결과적으로 복잡한 주기함수를 간단한 주기함수로 나타내기 위함.

#### - DFT, FFT

이산 푸리에 변환(DFT : Discrete Fourier Transform)
이산화된 시간 영역의 데이터를 이산화된 주파수 영역으로 변환해주는 알고리즘.

고속 푸리에 변환(FFT : Fast Fourier Transform) - 
연속된 영역에서 처리함으로써 이산 푸리에 변환의 계산량을 줄이는 알고리즘.

#### 1. 푸리에 해석

해석하고자 하는 함수의 차원을 변경하여 다른 시각에서 상태를 관측할 수 있다.
다음과 같이 두 가지 방법으로 나눔.

        - 푸리에 급수, 푸리에 적분 

##### 급수

<p align="center"><img src="https://user-images.githubusercontent.com/45933225/80908460-f843fe00-8d5a-11ea-83a8-aed8ec14a33e.png" width="25%"></p>

<p align="center"><img src="https://user-images.githubusercontent.com/45933225/80908450-e5c9c480-8d5a-11ea-9b00-b5c24713c81d.png" width="8%"></p>

값이 특정한 값으로 수렴하는지 아니면 (음, 양) 무한대로 발산을 하는지 판단.

##### 급수의 변화

       - 테일러 급수 -> 매클로린 급수 -> 푸리에 급수

##### - 테일러 급수

<p align="center"><img src="https://user-images.githubusercontent.com/45933225/80908438-c6329c00-8d5a-11ea-97b4-2dcb6d966589.png" width="70%"></p>

##### - 매클로린 급수

<p align="center"><img src="https://user-images.githubusercontent.com/45933225/80908443-d185c780-8d5a-11ea-95c2-0fb31237ed27.png" width="70%"></p>

##### - 푸리에 급수(Fourier Series)
주기가 있는 임의의 함수를 삼각함수의 급수로 바꾸어 나타내는 방법.

<p align="center"><img src="https://user-images.githubusercontent.com/45933225/80908399-88ce0e80-8d5a-11ea-9e8a-4c3002e576f1.png" width="50%"></p>

위 a(0)은  y절편의 이동을 나타냄으로써 따로 표기한 이유는 cos(0) = 1 sin(0) = 0의 값을 지니기 때문이다.
a(0), a(n), b(n)은 각각의 성분(가중치)가 sin, cos 포함도를 결정한다.

##### 오일러 공식(e^x)

<p align="center"><img src="https://user-images.githubusercontent.com/45933225/80908415-a69b7380-8d5a-11ea-8105-df8886b072f2.png" width="50%"></p>

<p align="center"><img src="https://user-images.githubusercontent.com/45933225/80908410-9edbcf00-8d5a-11ea-86ce-0c8ef9c496b2.png" width="50%"></p>

오일러 공식의 유도

1. 삼각함수의 직교성(Orthogonal Function)
삼각함수 계의 각 함수들은 한 주기 구간에서 서로 직교함.

<p align="center"><img src="https://user-images.githubusercontent.com/45933225/80908431-b3b86280-8d5a-11ea-853f-5bc20e36cfff.png" width="50%"></p>

삼각함수는 서로 직교하므로 따라서 두 함수를 내적하면 0이 나옴.
이어서 함수에서도 공간에서 정의된 두 직교 함수의 내적은 0이다.

##### 푸리에 합성

<p align="center"><img src="https://user-images.githubusercontent.com/45933225/80908387-79e75c00-8d5a-11ea-80c8-0319cc402aad.png" width="50%"></p>

위와 같이 분석을 하였을 때 각 함수의 가중치 비율을 알 수 있으며 주기를 선형조합하므로 다음과 같이 합성 그래프를 그릴 수 있다.

비교적으로 선형대수학은 계수의 합은 유한하지만 푸리에는 무한 급수 합을 구한다.


----아직------
- 푸리에 적분(Fourier Integral)
주기가 없는 함수라도, 삼각함수의 급수로 나타내는 방법.


