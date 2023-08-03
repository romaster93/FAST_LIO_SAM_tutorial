# FAST LIO2 SAM tutorial

본 포스트는 FAST-LIO2 와 LIO-SAM의 backend 부분을 결함한 모델이다. <br>
FAST-LIO2에는 Loop closing 부분이 없기 때문에 drift가 발생하더라도 보정이 되지 않는다. 따라서 이러한 모델을 사용하는게 이점이 있을 수 있다.<br>
특별한 작업이 들어간건 아니고 그냥 node 별로 연결 시켜준 형태라서 이해하기도 편하다. (실제로 따로 작동한다) <br>

참조 링크 : https://github.com/kahowang/FAST_LIO_SAM <br>

설치는 매우 간단하다. 아래 command를 따라 설치하면 된다. <br>

주의할점은 기존에 설치해놨던 FAST-LIO2 나 livox ros driver가 있다면 따로 backup해두고 설치를 진행해야한다. <br>


    cd catkin_ws/src
    git clone https://github.com/kahowang/FAST_LIO_SAM.git
    cd ..
    catkin build

config 파일이나 launch 파일은 FAST-LIO2 tutorial을 참고해서 수정한다. <br>

기능적으로 참고해야될 부분은 PCD파일을 저장하거나 pose를 저장할 때 rosservice를 통해서 save를 진행하면된다. <br>

    rosservice call /save_map "resolution: 0.0 destination: ''" 
    rosservice call /save_pose "resolution: 0.0 destination: ''" 

