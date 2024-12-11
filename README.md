# LineTracer2

https://youtu.be/yN9DHyjrEjs?si=2J4B-x0-0sXSzrzR

https://youtu.be/N9MKEoIQHDc?si=6Mp1-qmXvE9hSJ5O

https://github.com/vinpple/LineTracer2/blob/4036997df9da68cef0922b58873df8a5038d170f/main.cpp#L33-L37

다이나믹셀 초기화

https://github.com/vinpple/LineTracer2/blob/4036997df9da68cef0922b58873df8a5038d170f/main.cpp#L75-L76

straightSpeed: 기본 직진 속도.

k: 속도 제어를 위한 게인 값. (값이 클수록 작게 돌음 여러 번의 실험 결과 0.13정도가 적합)

https://github.com/vinpple/LineTracer2/blob/4036997df9da68cef0922b58873df8a5038d170f/main.cpp#L147-L152

bestCenter.x는 현재 검출된 최적 중심의 x좌표입니다.

frame.cols / 2는 영상의 가로 길이의 절반으로, 영상의 중앙 x좌표입니다.

error는 최적 중심이 영상 중앙에서 얼마나 벗어났는지를 나타내며, 왼쪽으로 벗어나면 음수, 오른쪽으로 벗어나면 양수가 됩니다.

straightSpeed는 모터의 기본 직진 속도입니다(100)

k는 에러에 대한 게인(조정 상수)입니다. 에러가 클수록 속도 차이가 크게 나도록 조정합니다.

vel1: 왼쪽 모터 속도입니다. 에러에 비례해 조정되므로 오른쪽으로 꺾으려면 왼쪽 모터 속도를 줄입니다.

vel2: 오른쪽 모터 속도입니다. 방향을 반대로 설정하기 위해 -(straightSpeed + k * error)로 설정합니다.

모터 속도 범위를 -200에서 200 사이로 제한합니다.

max와 min 함수를 사용하여 속도가 이 범위를 벗어나지 않도록 합니다.

https://github.com/vinpple/LineTracer2/blob/4036997df9da68cef0922b58873df8a5038d170f/main.cpp#L154-L157

mx.setVelocity(vel1, vel2) 함수는 왼쪽 모터와 오른쪽 모터에 각각 vel1과 vel2 속도를 설정합니다.

설정에 실패하면 오류 메시지를 출력하고 반복문을 종료합니다.

