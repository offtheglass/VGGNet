# VGGNet

## configuration

![initial](https://user-images.githubusercontent.com/86214286/195825524-ec8e1a9d-217a-436c-8b24-b9d33d6247a3.jpg)

* input size: 224X224X3
* convolutional filter로 3X3 계속 사용
* convolutional filter-activation-maxpooling의 구조 반복-->receptive field 넓어짐

### 3*3의 장점
* 필터를 많이 거치도록 해서 discrimination이 잘 되게 함.
  * 7X7을 한 번 적용하는 것보다 3X3을 3번 적용하는 게 discrimination이 잘 됨(non-linearity)
* parameter의 개수를 줄여서 학습속도가 빨라짐    

## training
* Batch Size:256
* Momentum:0.9
* L2 Regularization: 5X10^(-4)
* Learing rate:10^(-2)(validation set에서 성능향상이 없을 때마다 10^(-1))
* input image:224*224*3
### initialization
* A를 먼저 학습시키고 A로 처음 4개의 layer와 마지막 3개 fully connected layer를 initialization
* 나머지는 N(0,10^(-2))에서 뽑아서 initialization
* bias는 0
### scaling
#### single scale
* scale size를 하나로 고정한 뒤 224X224를 뽑음
#### multi scale
* scale size를 256에서 512 중 random하게 정한 뒤 224X224를 뽑음
### testing

## performance
* 19 layer 까지는 layer의 수를 늘리면 성능이 좋아짐, 그 이후는 유의미한 성능 변화 볼 수 없음
* multi scale로 train됐을 떠 더 좋은 성능을 
