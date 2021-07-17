# 유니티 기본학습


## Fundamentals
### 1. LTS:long time support	


### 2. Documentation check: 오프라인에서도 라이브러리를 사용할 수 있게 함.


### 3. .mtl(material library file): obj의 재질 속성 정보를 저장. 


파일 구조:  newmtl(새로운 머티리얼을 나타냄. 여러개라면 여러 재질을 사용.) https://timeboxstory.tistory.com/87?category=803210


<img width="186" alt="캡처" src="https://user-images.githubusercontent.com/48555909/125397034-58671300-e3e8-11eb-8bd5-2f01bc6b3e8f.PNG">


### 4. Templates: 2D, 3D, High Definition RP(HDRP. 그래픽에 최적화), Universal Render Pipeline(그래픽에 최적화)


### 5. 상단의 Gizmos : 스폐셜 오브젝트를 모두 보여줌.


### 6. Project tab-show in folder: .mata파일이 보임.


*shift+space: 선택한 탭 꽉 채우기.


*ctrl+p: 렌더플레이


*F: 오브젝트 클릭 후 - 프레임


*alt: 오브젝트 클릭 후 - 눈 모양으로 변함 - 오브젝트 중심으로 회전.


*V: 오브젝트 클릭 후 - 모서리를 선택 - 중앙을 잡고 객체이동. 스냅을 준다.

### 7. Package Manager: 프로젝트의 다양한 요구 사항에 적합한 기능.

### **-★★★ProBuilder를 Install** : tools->probuilder window. 오브젝트, 점, 선, 면으로 객체를 생성할 수 있다. https://unity3d.com/kr/unity/features/worldbuilding/probuilder 

<img width="316" alt="캡처" src="https://user-images.githubusercontent.com/48555909/125590978-96e1214c-cc34-40a9-9982-286bd755a6f3.PNG">

*New Poly Shape: 점을 연결하여 객체를 생성.

*Extrude Faces: 면을 뽑는다.

*New Shape: cube 생성.

*Filp Normals: 투명하게 볼 수 있음.

*Insert Edge Loop: 블랜더의 나이프.


### -Post Processing을 Install : Volume을 사용할 수 있다.

**Volume**: 후처리 작업. 영상에 필터와 효과를 적용. 

GameObject->Volume->Grobal Volume->profile의 new->Bloom추가. Threshold, Intensity조절.->Camera에서  Post Processing체크, anti-aliasing에서 첫번째거 선택.


### 8. **Per Object Limte**: 허용되는 빛의 수 제한. 멀리있는 right가 동작하지 않을 때. project setting->Graphics->Scriptable Render Pipeline Settings의 오브젝트 클릭->inspector에서 per object limie값 조절.



## Materials and Lighting

### 1. Materials : 재질 클래스를 나타냄. 
-대부분의 meterial이 shader가 standard로 설정되어 있다.   
-Albedo: 텍스처 이미지 파일, 색상을 넣을 수 있다.
## mesh Renderer
### 2. Lighting : 
































