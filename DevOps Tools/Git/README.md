깃
============
* '형상 관리'를 하기 위해 사용하는 것.
* 소스 코드의 버전 관리, 프로젝트 산출물에 대한 이력 관리(추적할 수 있도록)    
       
      
      
       
깃은 어떻게 형상 관리를 하는가
-------------------------------
  
  
* 깃의 두 가지 저장소 개념
1. Remote repository   
   
2. Local repository   
     
     
      
<img src="https://user-images.githubusercontent.com/75105871/121289051-55778f00-c91f-11eb-9a33-1537e119ee1f.jpg"/>
      
      
**작업트리에서 작업한 내용을 내 Local에 먼저 저장하고, Local에 저장된 것을 다시 Remote에 저장(Upload)해야 한다.**    
     
1>    
-1. 작업트리에서 형상 관리 하고싶은 대상 파일들을 인덱스에 등록(공연 무대에 설 대상들을 리스트업) __(git add)__      
    인덱스에 등록하지 않은(깃에 add로 추가하지 않은) 것은 레포지토리에 저장 불가    
-2. 인덱스에 추가된 파일을 로컬 레포지토리에 저장(리스트에 있는 출연진들 리허설 무대/사전 녹화, 아직 방송 X) __(git commit)__
    
2>        
로컬 레포지토리에 저장된 내용을 원격 레포지토리에 저장(모든 사람들이 볼 수 있게 방송 송출) __(git push)__     
모두와 공유할 수 있는 상태가 된 것
    
3>    
협업을 위해서 사용자B는 A와 같은 환경을 갖고 있어야 함. 이를 위해 원격 레포지토리에 있는 것을 복제해 옴 __(git clone)__   
두 사용자 모두 원격 레포와 똑같은 상태가 됨.
     
* 이후 추가 정리할 내용

하나의 프로젝트를 공유해서 쓸 때 충돌이 나거나, 환경적인 문제로 프로젝트를 가져올 때 문제가 생길 수 있음
-> 깃의 관리 대상에서 제외할 ignore 파일 관리