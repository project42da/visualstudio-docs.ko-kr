---
title: "셰이더 작업 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6b2ea1ed-b995-4e75-af19-c68fd37a3bc5
caps.latest.revision: 8
author: "BrianPeek"
ms.author: "brpeek"
manager: "ghogen"
caps.handback.revision: 8
---
# 셰이더 작업
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에서 그래프 기반 셰이더 디자이너를 사용하여 사용자 지정 셰이더 효과를 디자인할 수 있습니다.  DirectX 기반 게임 또는 응용 프로그램에서 이러한 셰이더를 사용할 수 있습니다.  
  
## 셰이더  
 *셰이더*는 꼭짓점 변환 또는 픽셀 색 지정과 같은 그래픽 계산을 수행하는 컴퓨터 프로그램으로 일반적으로 CPU 대신 GPU\(그래픽 처리 장치\)에서 실행됩니다.  기능이 고정된 기존 그래픽 파이프라인의 단계 대부분은 현재 셰이더 프로그램에 의해 수행되기 때문에 앱에서 필요한 대로 파이프라인을 만드는 데 사용할 수 있습니다.  
  
 가장 일반적인 종류의 셰이더는 꼭지점 별 계산을 수행하고 비프로그래밍 그래픽 하드웨어에서 고정 함수 변환 및 조명 회로를 교체하는 *꼭지점 셰이더*와 픽셀의 색을 지정하고 비프로그래밍 그래픽 하드웨어에서 고정 함수 색 조합기 회로를 교체하는 픽셀 당 계산을 수행하는 *픽셀 셰이더*입니다.  최신 그래픽 하드웨어로 더 많은 종류의 셰이더 즉, *헐 셰이더*, *도메인 셰이더* 및 그래픽 계산용 *기하 도형 셰이더* 및 비그래픽 계산용 *계산 셰이더*가 가능해졌습니다.  이러한 단계는 프로그래밍 할 수 없는 그래픽 하드웨어에도 사용할 수 없습니다.  기본적으로 셰이더는 병렬 데이터\-병렬\(SIMD\) 및 그래픽 중심\(내적\) 지침을 제공하는 어셈블리 같은 언어를 사용하여 만들었습니다.  이제 셰이더는 일반적으로 HLSL\(High Level Shader Language\) 같은 상위 수준의 C\-같은 언어를 사용하여 만들어집니다.  
  
 셰이더 디자이너를 사용하여 코드를 입력하고 컴파일하는 대신 대화 형식으로 픽셀 셰이더를 만들 수 있습니다.  셰이더 디자이너에서 셰이더를 통해 데이터 값의 흐름과 중간 결과를 나타내는 노드 사이의 데이터, 작업 및 연결을 표시하는 많은 수의 노드로 셰이더를 정의합니다.  이 접근 방식과 셰이더 디자인의 실시간 미리 보기를 사용하여 셰이더 실행을 보다 쉽게 시각화할 수 있으며 실험을 통해 흥미로운 셰이더 변형을 '검색'할 수 있습니다.  
  
## DGSL 문서  
 셰이더 디자이너는 DGML\(Directed Graph Markup Language\)에 기반한 XML 형식인 DGSL\(Directed Graph Shader Language\)에 셰이더를 저장합니다.  모델 편집기에서 DGSL 셰이더를 3차원 모델에 적용할 수 있습니다.  그러나, 응용 프로그램에서 DGSL 셰이더를 사용하기 전에 HLSL과 같은 DirectX가 인식할 수 있는 형식으로 내보내야 합니다.  
  
 DGSL은 DGML과 호환되므로 DGSL 셰이더를 분석하기 위해 DGML 문서를 분석하도록 설계된 도구를 사용할 수 있습니다.  DGML 요소에 대한 자세한 내용은 [Understanding Directed Graph Markup Language \(DGML\)](http://msdn.microsoft.com/library/ee842619.aspx)를 참조하십시오.  
  
## 관련 항목  
  
|제목|설명|  
|--------|--------|  
|[셰이더 디자이너](../designers/shader-designer.md)|[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 셰이더 디자이너를 사용하여 셰이더 작업을 수행하는 방법을 설명합니다.|  
|[셰이더 디자이너 노드](../designers/shader-designer-nodes.md)|그래픽 효과를 달성하는 데 사용할 수 있는 셰이더 디자이너 종류를 설명합니다.|  
|[셰이더 디자이너 예제](../designers/shader-designer-examples.md)|일반적인 그래픽 효과를 달성하기 위해 셰이더 디자이너를 사용하는 방법을 보여주는 항목에 대한 링크를 제공합니다.|