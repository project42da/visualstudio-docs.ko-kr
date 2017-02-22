---
title: "순차 워크플로 뷰(레거시) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
helpviewer_keywords: 
  - "순차 워크플로 뷰"
  - "순차 워크플로, 뷰"
ms.assetid: 135f24b9-1b37-442b-9ef8-f0f2108a3212
caps.latest.revision: 7
caps.handback.revision: 7
author: "ErikRe"
ms.author: "erikre"
manager: "erikre"
---
# 순차 워크플로 뷰(레거시)
[!INCLUDE[vs2010](../modeling/includes/vs2010_md.md)]에서는 [!INCLUDE[netfx35_long](../workflow-designer/includes/netfx35_long_md.md)] 또는 [!INCLUDE[vstecwinfx](../workflow-designer/includes/vstecwinfx_md.md)]를 대상으로 하는 데 사용할 수 있는 레거시 [!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)]를 제공합니다.  
  
 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)]에서는 친숙한 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 사용자 인터페이스를 사용하여 [!INCLUDE[wf](../workflow-designer/includes/wf_md.md)] 응용 프로그램을 시각적으로 만들 수 있습니다.[!INCLUDE[wf](../workflow-designer/includes/wf_md.md)] 응용 프로그램은 활동이라고 하는 워크플로 프로세스 단계로 구성됩니다.워크플로를 만들려면 **도구 상자**의 해당 활동 디자이너를 디자이너 화면으로 끌어 와 디자인 화면에 활동을 구성합니다.  
  
 순차 워크플로인 [SequentialWorkflowActivity](http://go.microsoft.com/fwlink?LinkID=65040)를 만들 경우 세 가지 워크플로 뷰를 사용할 수 있습니다.**워크플로** 메뉴와 디자인 화면의 상황에 맞는 메뉴에서 이러한 뷰에 액세스할 수 있습니다.  
  
 다음 표에서는 각 뷰의 이름과 설명을 보여 줍니다.  
  
|메뉴\/탭 옵션|설명|  
|--------------|--------|  
|**순차 워크플로 보기**|디자인 화면을 마우스 오른쪽 단추로 클릭하고 상황에 맞는 메뉴에서 **SequentialWorkflow 보기** 옵션을 선택하여 **순차 워크플로** 뷰가 표시되도록 합니다. 이 뷰에는 순차 워크플로가 활동을 기반으로 그래픽으로 표현됩니다.또는 **워크플로** 메뉴에서 **순차 워크플로 보기**를 선택합니다.|  
|**취소 핸들러 보기**|디자인 화면을 마우스 오른쪽 단추로 클릭하고 상황에 맞는 메뉴에서 **취소 핸들러 보기** 옵션을 선택하여 **순차 워크플로** 뷰가 표시되도록 합니다. 이 뷰에는 워크플로와 연결된 [CancellationHandlerActivity](http://go.microsoft.com/fwlink?LinkID=65050) 활동이 표시됩니다.또는 **워크플로** 메뉴에서 **취소 핸들러 보기**를 선택합니다.|  
|**오류 핸들러 보기**|디자인 화면을 마우스 오른쪽 단추로 클릭하고 상황에 맞는 메뉴에서 **오류 핸들러 보기** 옵션을 선택하여 **오류** 뷰를 표시합니다. 이 뷰에는 워크플로와 연결된 [FaultHandlersActivity](http://go.microsoft.com/fwlink?LinkID=65055) 활동이 표시됩니다.또는 **워크플로** 메뉴에서 **오류 핸들러 보기**를 선택합니다.|  
  
 유사한 뷰에 대한 자세한 내용은 [활동 뷰\(레거시\)](../workflow-designer/activity-views-legacy.md)를 참조하십시오.  
  
## 참고 항목  
 [활동 뷰\(레거시\)](../workflow-designer/activity-views-legacy.md)   
 [레거시 워크플로 프로젝트 만들기](../workflow-designer/creating-legacy-workflow-projects.md)   
 [워크플로 제작 모드](http://go.microsoft.com/fwlink?LinkID=65014)