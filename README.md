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
