---
title: "활동 뷰(레거시) | Microsoft Docs"
ms.custom: ""
ms.date: "11/24/2016"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
helpviewer_keywords: 
  - "활동, 활동 뷰"
  - "활동 뷰"
  - "뷰, 활동(activity)"
ms.assetid: 83dc68cd-2cb2-45c2-9a6e-10d82053171a
caps.latest.revision: 5
caps.handback.revision: 5
author: "ErikRe"
ms.author: "erikre"
manager: "erikre"
---
# 활동 뷰(레거시)
[!INCLUDE[wf](../workflow-designer/includes/wf_md.md)]에서 제공하는 많은 활동은 워크플로를 구성하는 데 사용되며 이러한 활동에는 레거시 [!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)]에서 사용할 수 있는 몇 가지 디자인 뷰가 있습니다.**도구 상자**에서 디자인 화면으로 활동 디자이너를 끌어 올 때와 그 이후에 활동을 선택할 때마다 **워크플로** 메뉴를 사용하거나 선택된 활동을 마우스 오른쪽 단추로 클릭하는 방법으로 여러 디자인 뷰를 전환할 수 있습니다.또한 선택된 항목의 이름 위로 포인터를 옮기면 드롭다운 탭 집합이 나타나 여러 뷰 사이를 전환할 때 사용할 수 있습니다.  
  
 모든 활동에는 적어도 하나의 뷰가 있으며 이 뷰는 **도구 상자**에서 디자인 화면으로 활동 디자이너를 끌 때 표시되는 기본 뷰입니다.이 활동 기본 뷰는 메뉴 및 탭의 **\[활동 유형\] 보기** 옵션으로 제공됩니다\(예: **병렬 보기**\).대부분의 활동에 추가 뷰가 있으며, 활동마다 서로 다른 뷰를 가질 수 있습니다.예를 들어, [TransactionScopeActivity](http://go.microsoft.com/fwlink?LinkID=65093)\(영문 페이지일 수 있음\) 활동은 보정 뷰를 가지며, [EventHandlingScopeActivity](http://go.microsoft.com/fwlink?LinkID=65030)\(영문 페이지일 수 있음\) 활동은 이벤트 뷰를 가집니다.Windows Workflow Foundation에서 제공하는 활동 중 상당수에는 **취소 핸들러 보기** 및 **오류 핸들러 보기** 디자인 뷰가 있어, 활동과 연결된 [CancellationHandlerActivity](http://go.microsoft.com/fwlink?LinkID=65050)\(영문 페이지일 수 있음\) 및 [FaultHandlersActivity](http://go.microsoft.com/fwlink?LinkID=65055)\(영문 페이지일 수 있음\)를 볼 수 있습니다.  
  
 다음 표에서는 각 뷰의 이름과 설명을 보여 줍니다.  
  
|메뉴\/탭 옵션|설명|  
|--------------|--------|  
|**\[활동 유형\] 보기**|선택한 활동의 기본 그래픽 표현을 보려면 이 메뉴 또는 탭 옵션을 선택합니다.|  
|**취소 핸들러 보기**|선택한 활동과 연결된 [CancellationHandlerActivity](http://go.microsoft.com/fwlink?LinkID=65050)\(영문 페이지일 수 있음\)를 보려면 이 메뉴 또는 탭 옵션 뷰를 선택합니다.|  
|**오류 핸들러 보기**|선택한 활동과 연결된 [FaultHandlersActivity](http://go.microsoft.com/fwlink?LinkID=65055)\(영문 페이지일 수 있음\)를 보려면 이 메뉴 또는 탭 옵션 뷰를 선택합니다.|  
|**보정 핸들러 보기**|선택한 [TransactionScopeActivity](http://go.microsoft.com/fwlink?LinkID=65093)\(영문 페이지일 수 있음\)와 연결된 [CompensationHandlerActivity](http://go.microsoft.com/fwlink?LinkID=65053)\(영문 페이지일 수 있음\)를 보려면 이 메뉴 또는 탭 옵션 뷰를 선택합니다.|  
|**이벤트 핸들러 보기**|선택한 [EventHandlingScopeActivity](http://go.microsoft.com/fwlink?LinkID=65030)\(영문 페이지일 수 있음\)와 연결된 [EventHandlersActivity](http://go.microsoft.com/fwlink?LinkID=65018)\(영문 페이지일 수 있음\)를 보려면 이 메뉴 또는 탭 옵션 뷰를 선택합니다.|  
  
 유사한 뷰에 대한 자세한 내용은 [순차 워크플로 뷰\(레거시\)](../workflow-designer/sequential-workflow-views-legacy.md)를 참조하십시오.  
  
## 참고 항목  
 [레거시 워크플로 활동](../workflow-designer/legacy-workflow-activities.md)   
 [순차 워크플로 뷰\(레거시\)](../workflow-designer/sequential-workflow-views-legacy.md)