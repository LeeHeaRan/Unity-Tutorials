# 유니티 기본학습


## Fundamentals
 1. LTS:long time support	   
 2. Documentation check: 오프라인에서도 라이브러리를 사용할 수 있게 함.   
 3. .mtl(material library file): obj의 재질 속성 정보를 저장.    
파일 구조:  newmtl(새로운 머티리얼을 나타냄. 여러개라면 여러 재질을 사용.) https://timeboxstory.tistory.com/87?category=803210

<img width="186" alt="캡처" src="https://user-images.githubusercontent.com/48555909/125397034-58671300-e3e8-11eb-8bd5-2f01bc6b3e8f.PNG">

 4. Templates: 2D, 3D, High Definition RP(HDRP. 그래픽에 최적화), Universal Render Pipeline(그래픽에 최적화)   
 5. 상단의 Gizmos : 스폐셜 오브젝트를 모두 보여줌.   
 6. Project tab-show in folder: .mata파일이 보임.   
*shift+space: 선택한 탭 꽉 채우기.   
*ctrl+p: 렌더플레이   
*F: 오브젝트 클릭 후 - 프레임   
*alt: 오브젝트 클릭 후 - 눈 모양으로 변함 - 오브젝트 중심으로 회전.   
*V: 오브젝트 클릭 후 - 모서리를 선택 - 중앙을 잡고 객체이동. 스냅을 준다.   
 7. Package Manager: 프로젝트의 다양한 요구 사항에 적합한 기능.

 **-ProBuilder를 Install** ★★★ : tools->probuilder window. 오브젝트, 점, 선, 면으로 객체를 생성할 수 있다. https://unity3d.com/kr/unity/features/worldbuilding/probuilder 

<img width="316" alt="캡처" src="https://user-images.githubusercontent.com/48555909/125590978-96e1214c-cc34-40a9-9982-286bd755a6f3.PNG">

*New Poly Shape: 점을 연결하여 객체를 생성.   
*Extrude Faces: 면을 뽑는다.   
*New Shape: cube 생성.   
*Filp Normals: 투명하게 볼 수 있음.   
*Insert Edge Loop: 블랜더의 나이프.      
**-Post Processing을 Install** : Volume을 사용할 수 있다.   
**Volume**: 후처리 작업. 영상에 필터와 효과를 적용.    
-GameObject->Volume->Grobal Volume->profile의 new->Bloom추가. Threshold, Intensity조절.->Camera에서  Post Processing체크, anti-aliasing에서 첫번째거 선택.   
 8. **Per Object Limte**: 허용되는 빛의 수 제한. 멀리있는 right가 동작하지 않을 때. project setting->Graphics->Scriptable Render Pipeline Settings의 오브젝트 클릭->inspector에서 per object limie값 조절.   

## Materials and Lighting   
 1. Materials : 재질과 관련된 객체. 
-대부분의 meterial이 shader가 standard로 설정되어 있다.   
-HDRP: https://unity.com/kr/how-to/getting-started-high-definition-render-pipeline-hdrp-games   
-**High Definition Materials**를 사용하기 위해서는 Edit-Render Pipeline-Upgrade Selected Materials to High Definition Materials로 설정해야한다. Shader를 HDRP/Lit로 변경. Surface Inputs의 Base Map에 텍스쳐를 넣어준다.   *불러온 객체가 보라색일 때 해결법   
-Albedo: 기본 standard. 텍스처 이미지 파일, 색상을 넣을 수 있다.   
 Base Map(.tif/.png): 색상과 텍스쳐를 설정. Texture Type: Defauit   
 Normal Map(.tif): 빛에 대한 굴곡을 설정. Texture Type: Nomal map   
-노멀맵 만들기: 텍스쳐 이미지를 복사 - Texture Type: Nomal map으로 변경, filtering: sharp 또는 Smooth 선택 - Apply - nomal map생성!      
*Emission - Tiling: 가로 세로 갯수 조절

 2. Lighting : 빛과 관련된 객체.
-종류: Directional Light, Point Light, Spotlinght, Area Light, Planar Reflecion Probe, Reflecction Probe, Light Probe Group   
 Area Light: Shape-Shape로 모양 설정이 가능.   
 Point Light: Mode에서 설정 가능. 
####-Lighting Seting-Lighting-Scene-new lighting settings: 기본 라이팅 설정. https://docs.unity3d.com/kr/2018.4/Manual/GlobalIllumination.html   
 LightMap Resoultion: 퀄리티 조절. 높을수록 하이퀄리티.
 Bounces : 반사 횟수 조절.
 point light->Emission->IndirectMultipiler조절후 적용하기 위해서는 lighting setting에서 GenerateLighting을 해야함. =>귀찮으니까 Auto Generate해놓자.
*Indirect Multiplier: 간접광과 환경광의 영향력을 조절한다.   
*Baked lightimaps: 작은 텍스쳐.   


## 키워드로 학습하기.   
### Materials and Lighting   
1. Reflection Probe : 라이팅의 한 종류. 금속 같은 반사를 만들어냄. 박스로 빛에 반사되는 물체의 반사정도를 조절할 있음. capture setting으로 반사되는 물체의 위치를 조절가능.   
2. new Material->Emission inputs : 빛이 나는 메터리얼을 만들어냄. Use Emission Intensity 를 check. Emission Intensity->EV100 
3. ---Light->Shadows->Update Mode: 그림자 연산처리에 오래 걸림. 조절 할 수있음.
4. ---Light->Shadows->Resoultion: 그림자의 엣지를 조절 할 수 있음.
5. Light->Sence->Lihthmap Resolution: 퀄리티를 조절함. Scence창의 왼쪽 상단의 shaded의 Albedo로 확인 할 수 있음.
6. Light Probe Group: 빛에 의해 반사된 색상이 오브젝트에게 반사색으로 보이는데 영향을 주는 반사빛들을 연결하여 볼수 있게 해줌.
7. Inspector->Add Componet->OcclusionArea: ....터레인에서 카메라 화면에만 보이는 부분을 만듬. bake를 사용함. bake가 뭐지???   
8. Voloum->Global Voloume:Inspector->Profile->new->add Overrid->Post Processing->**Bloom.** Thresold, Intensity를 check. 언리얼의 쨍한 느낌도 가능함. Scene창에서 왼쪽 상단에 Post Processings를 체크하면 확인 할 수 있음.   
8-1. Inspector->Profile->new->add Overrid->color Curves:   
8-2. Inspector->Profile->new->add Overrid->Post Processing->Vignette: color, intersity, smoothness, rounded를 체크. 화면 테두리를 날림.   
8-3. Inspector->Profile->new->add Overrid->Post Processing->Depth Of Field: 블러처리를 할 수 있음. 초점을 맞춤. Focus Distance로 거리에 따라 블러를 처리할 수 있다.   
### UI and 2D Games

### 애니메이션
스켈레톤/본
조인트
베이크
스킨

1. 오브젝트를 한쪽 방향으로 계속 돌는 애니메이션만들기: 스크립트(Rotator.s)를 만든다. Update()안에 transform.Rotate(transform.up, RotSpeed * Time.deltaTime)을 작성하고 오브젝트에게 스크립트를 넣는다.   
2. AnimationCurve, 시간적으로 변화가 있는 애니메이션 만들기: 스크립트(Mvoe.s)를 만든다. **소스파일 참조.**   
3. Animation Event: Animator창에서 Add Event로 만든다.   
![제목 없음-1](https://user-images.githubusercontent.com/48555909/130547635-8f77c069-a6ee-4c06-9ec6-ec4760b4a4c1.png)   
4. Animation Clip: 시간과 관계됨.
*해당 애니메이션이 있는 캐릭터가 없다면 애니메이션은 실행되지 않는다.
5. Rig의 Anumation type: 애니메이션 타입을 정할 수 있다.
6. Animator 컴포넌트: Animator 창을 열어 노드로 조작할 수 있다.
7. Animation Controller: Animator컴포넌트 안에 넣는 컨트롤러.

