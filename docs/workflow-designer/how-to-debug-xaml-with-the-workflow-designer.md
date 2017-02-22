---
title: "방법: Workflow Designer로 XAML 디버그 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: d9305dbc-af62-4bdd-b03f-c54e3fe9ecc7
caps.latest.revision: 8
caps.handback.revision: 8
author: "ErikRe"
ms.author: "erikre"
manager: "erikre"
---
# 방법: Workflow Designer로 XAML 디버그
워크플로는 XAML로 정의됩니다.워크플로의 UI 표현은 해당 워크플로를 정의하는 XAML 트리의 맨 위에 빌드됩니다.디버깅 환경은 [!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)]의 워크플로 디버깅과 비슷합니다.예를 들어 XAML을 디버깅할 때 로컬, 조사식 및 스레드 창은 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] 디버깅에서와 동일한 방식으로 작동합니다.또한 XAML 디버깅 중의 호출 스택 보기는 워크플로에 대한 실행 흐름의 줄 기반 계층 보기입니다.  
  
> [!NOTE]
>  워크플로의 XAML이 활동과 동일한 어셈블리에 있는 경우 클래스 이름의 어셈블리 부분이 포함되지 않습니다.클래스 \(활동\) 이름의 이 부분이 없으면 XAML을 런타임에 로드할 수 없습니다.기본 프로젝트와 같은 네임스페이스에 활동을 정의하지 않는 것이 좋습니다. 그렇지 않으면 XAML을 디자이너에서 편집한 후에 수작업으로 편집해야 합니다.  
  
### 워크플로 XAML을 디버깅하려면  
  
1.  [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에서 워크플로 또는 활동 프로젝트를 엽니다.  
  
2.  [방법: 워크플로에 중단점 설정](../Topic/How%20to:%20Set%20Breakpoints%20in%20Workflows.md)에서 설명한 대로 디버깅할 활동의 중단점을 설정합니다.  
  
3.  워크플로 정의가 포함된 .xaml 파일을 마우스 오른쪽 단추로 클릭하고 **코드 보기**를 선택합니다.디자인 뷰에서 중단점을 설정한 활동의 XAML 요소 선언과 같은 줄에 중단점이 표시됩니다.  
  
4.  [방법: 워크플로 디버거 호출](../workflow-designer/how-to-invoke-the-workflow-debugger.md)에서 설명한 대로 디버거를 호출합니다.  
  
5.  코드 실행이 중단점 중 하나에 도달하면 해당 중단점과 연결된 XAML 요소가 강조 표시됩니다.다음 중단점으로 이동하려면 **F10** 또는 **F11** 키를 사용합니다.  
  
## 참고 항목  
 [방법: 워크플로에 중단점 설정](../Topic/How%20to:%20Set%20Breakpoints%20in%20Workflows.md)   
 [방법: 워크플로 디버거 호출](../workflow-designer/how-to-invoke-the-workflow-debugger.md)