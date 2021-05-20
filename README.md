# 작업 스케줄링(Job Scheduling)

n개의 작업, 각 작업의 수행 시간, m개의 동일한 기계가 주어질 떄, 모든 작업이 가장 빨리 종료 되도록 작업을 기계에 배정하는 문제. 단, 한 작업은 배정된 기계에서 연속적으로 수행되어야 한다. 또한 기께는 1번에 하나의 작업만을 수행한다.

## 시간 복잡도
- n개의 작업을 하나씩 가장 빨리 끝나는 기계에 배정하고, 가장 일찍 끝나는 기계를 찾기 위해 반복문이 m-1번 수행된다. => nxO(n)
- 각 기계에 배정된 마지막 작업의 종료시간 살펴보기 : O(m)
- 따라서, 시간복잡도 : nO(m) + O(m) = O(nm)

## 근사 비율
근사해를 OPT'라 하고, 최적해를 OPT라고 할 떄, OPT' <= 2xOPT이다.
- 근사해는 최적해의 2배를 넘지 않는다.

### T <= T'를 이용한 증명
<img width="604" alt="작업스케줄링" src="https://user-images.githubusercontent.com/81741589/118929951-1c7f7680-b980-11eb-8f9f-9c5cce5052a8.png">
ㄴ
- T'은 작업 i를 제외한 평균 종료 시간이다. 따라서 작업 i가 배정된 기계를 제외한 모든 기계에 배정된 작업은 적어도 T 이후에 종료되기 때문에 T <= T'이 된다.
- T <= T' 관계를 이용한 OPT' <= 2xOPT 증명

<img width="535" alt="T =증명" src="https://user-images.githubusercontent.com/81741589/118929876-083b7980-b980-11eb-90de-4581aed4e3d5.png">

# Brute Force, Greedy 방식의 비교
- 최적해 : Brute Force
- 근사해 : Greedy
- 근사비율 : 근사해 / 최적해

![CamScanner 05-20-2021 17 21](https://user-images.githubusercontent.com/81741589/118960369-2dd77b80-b99e-11eb-9260-235799180087.jpg)


![CamScanner 05-20-2021 17 21 (1)](https://user-images.githubusercontent.com/81741589/118960118-eb15a380-b99d-11eb-9574-1c7649b19d9d.jpg)

![CamScanner 05-20-2021 17 22](https://user-images.githubusercontent.com/81741589/118960433-4051b500-b99e-11eb-8c12-3edc18b653a0.jpg)


|-----|2|3|4|5|
|-----|---|---|---|
|근사해|4|6|7|11|
|최적해|4|5|6|10|
|근사비울|1|1.2|1.1|1.1|