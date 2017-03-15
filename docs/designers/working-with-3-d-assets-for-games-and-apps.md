---
title: "게임 및 응용 프로그램을 위한 3D 자산 작업 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.graphics"
ms.assetid: 910d673b-c884-4eeb-9928-0e89f3d38cb6
caps.latest.revision: 24
author: "BrianPeek"
ms.author: "brpeek"
manager: "ghogen"
caps.handback.revision: 24
---
# 게임 및 응용 프로그램을 위한 3D 자산 작업
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이 문서에서는 DirectX 기반 게임 및 응용 프로그램에서 3 차원 모델, 텍스처 및 셰이더를 만들거나 수정하는 데 사용할 수 있는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 도구를 설명합니다.  
  
## Visual Studio에서 DirectX 응용 프로그램 개발  
 DirectX 응용 프로그램은 일반적으로 다양하고 상호 작용이 가능한 멀티미디어 경험을 제공하는 오디오 및 3차원 시각 에셋과 프로그래밍 논리, DirectX API 및 HLSL\(High Level Shading Language\) 프로그램을 결합합니다.  [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에는 IDE에서 다른 도구를 사용하지 않고 이미지, 텍스처, 3차원 모델 및 셰이더로 작업하는 데 사용할 수 있는 도구가 포함되어 있습니다.  Visual Studio 도구는 생산 준비 자산을 준비하기 전에 코드를 테스트하고 프로토타입을 구축하는 데 사용할 수 있는 *자리 표시자* 자산을 만들고 응용 프로그램에 디버깅할 프로덕션 준비 자산을 검사하고 수정하는 데 특히 적합합니다.  
  
 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에서 작업할 수 있는 자신 종류에 대한 자세한 내용은 다음과 같습니다.  
  
### 이미지 및 질감  
 이미지 및 질감은 게임 및 응용 프로그램에서 색상과 시각적 정보를 제공합니다.  3차원 그래픽에서 질감은 다양한 사용을 지원하도록 여러 가지 형식, 유형 및 기하 도형을 제공합니다.  예를 들어, 일반 맵은 3D 모델의 빛을 더욱 정밀하게하기 위해 표면의 픽셀 당 법선을 제공하고, 큐브 맵은 스카이 박싱, 반사, 구형 텍스처 매핑에 사용되는 것과 같이 전방향 텍스처를 제공합니다.  텍스처는 다른 세부 수준에서 효율적인 렌더링을 지원할 수 있도록 mip 맵을 제공하고 다른 색 채널 및 색 순서를 지원합니다.  텍스처는 전용 그래픽 메모리를 덜 차지하고 GPU가 텍스처에 더 효율적으로 액세스하는 데 도움을 주는 다양한 압축된 형식으로 저장할 수 있습니다.  
  
 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 이미지 편집기를 사용하여 여러 가지 일반적인 유형과 형식으로 이미지와 질감 작업을 할 수 있습니다.  
  
### 3D 모델  
 3\-D 모델은 게임과 응용 프로그램에 공간과 모양을 만듭니다.  적어도 모델은 3차원 공간에서 *꼭지점*이라는 점의 위치를 선이나 모델의 형태를 나타내는 삼각형을 정의하는 데이터를 인덱싱하면서 인코드합니다.  색 정보, 법선 벡터 또는 응용 프로그램 특정 특성 등의 추가 데이터를 이러한 꼭짓점에 연결할 수 있습니다.  각 모델은 또한 개체 범위 특성\-예를 들어, 개체 표면의 모양을 계산하는데 어떤 셰이더를 사용할 것인가, 또는 어떤 질감이 적용될 것인가\-을 정의할 수 있습니다.  
  
 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 모델 편집기를 사용하여 여러 가지 일반적인 형식으로 3차원 모델 작업을 할 수 있습니다.  
  
### 셰이더  
 셰이더는 그래픽 처리 장치\(GPU\)를 실행 하는 작은, 도메인별 프로그램입니다.  셰이더는 3차원 모델을 화면 셰이프로 변형하는 방법 및 이러한 셰이프에서 각 픽셀을 색으로 표시하는 방법을 결정합니다.  셰이더를 만들고 게임이나 앱에 개체를 적용하여 개체를 고유한 모양을 만들 수 있습니다.  
  
 그래프 기반 셰이더 디자인 도구인 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 셰이더 디자이너를 사용하여 HLSL 프로그래밍에 대한 지식 없이도 사용자 지정 시각적 효과를 만들 수 있습니다.  
  
> [!NOTE]
>  DirectX 프로그래밍을 시작 하는 방법에 대한 자세한 내용은 참조 [DirectX](http://go.microsoft.com/fwlink/p/?LinkId=224633).  DirectX 기반 앱을 디버깅하는 방법에 대한 자세한 내용은 [그래픽 진단\(DirectX 그래픽 디버그\)](../debugger/visual-studio-graphics-diagnostics.md)를 참조하십시오.  
  
## DirectX 버전 호환성  
 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]는 DirectX를 사용하여 2\-D 및 3\-D 자산을 렌더링합니다.  DirectX 11 렌더러 또는 WARP\(Windows Advanced Rasterization Platform\) 소프트웨어 렌더러를 선택할 수 있습니다.  DirectX 11 렌더러는 DirectX 11 및 DirectX 10 GPU에서 고성능, 하드웨어 가속 렌더링을 제공합니다.  WARP 렌더러를 사용하면 자산을 광범위한 컴퓨터에 작동할 수 있습니다. 이에는 최신 그래픽 하드웨어를 가지고 있지 않은 컴퓨터와 그래픽 하드웨어를 통합한 컴퓨터가 포함됩니다.  WARP에 대한 자세한 내용은, [Windows 고급 래스터화 플랫폼 \(구부리기\) 가이드](http://go.microsoft.com/fwlink/p/?LinkId=224634)를 참조하십시오.  
  
## 관련 항목  
  
|제목|설명|  
|--------|--------|  
|[질감 및 이미지 작업](../designers/working-with-textures-and-images.md)|[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]를 사용하여 이미지와 질감 작업을 수행하는 방법을 설명합니다.|  
|[3차원 모델 작업](../designers/working-with-3-d-models.md)|[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]를 사용하여 3\-D 모델 작업을 수행하는 방법을 설명합니다.|  
|[셰이더 작업](../designers/working-with-shaders.md)|[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 셰이더 디자이너를 사용하여 사용자 지정 셰이더 효과를 만들고 수정하는 방법을 설명합니다.|  
|[게임 또는 응용 프로그램에 3차원 자산 사용](../designers/using-3-d-assets-in-your-game-or-app.md)|게임 또는 응용 프로그램에서 이미지 편집기, 모델 편집기 또는 셰이더 디자이너를 사용하여 만든 자산을 사용하는 방법에 대해 설명합니다.|