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

그림

아날로그 신호(Analog Signal) - 연속시간 신호이면서 동시에 연속크기 신호
디지털 신호(Digital Signal) - 이산시간 신호이면서 동시에 이산크기 신호

아날로그 -> 디지털 신호 변환 과정(시간, 크기)

    1. 샘플링(Sampling) - 시간이 연속적이며 크기가 연속인 신호 시간을 이산으로 변환
    2. 양자화(Quantization) - 시간이 이산이며 크기가 연속인 신호 크기를 이산으로 변환

*무리수는 컴퓨터로 정확히 표현할 수 없어 특정한 값으로 양자화하므로 오차가 발생함.

## 푸리에 변환(FT : Fourier Transform)
시간에 대한 함수 (혹은 신호) 를 함수를 구성하고 있는 주파수 성분으로 분해하는 작업하는 것을 말함.

1. DFT, FFT

이산 푸리에 변환(DFT : Discrete Fourier Transform)
이산화된 시간 영역의 데이터를 이산화된 주파수 영역으로 변환해주는 알고리즘.

고속 푸리에 변환(FFT : Fast Fourier Transform) - 
연속된 영역에서 처리함으로써 이산 푸리에 변환의 계산량을 줄이는 알고리즘.


