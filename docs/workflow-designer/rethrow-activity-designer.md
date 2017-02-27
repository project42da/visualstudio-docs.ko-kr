---
title: "Rethrow 활동 디자이너 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "System.Activities.Statements.Rethrow.UI"
ms.assetid: 9cfa2eda-395f-4cf3-9154-83fadd4f7452
caps.latest.revision: 5
author: "ErikRe"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# Rethrow 활동 디자이너
**Rethrow** 활동 디자이너는 <xref:System.Activities.Statements.Rethrow> 활동을 만들고 구성하는 데 사용됩니다.  
  
## Rethrow 활동  
 <xref:System.Activities.Statements.Rethrow> 활동은 이전에 throw된 예외를 throw합니다.이 활동은 <xref:System.Activities.Statements.TryCatch> 활동의 <xref:System.Activities.Statements.Catch> 처리기에서만 사용할 수 있습니다.  
  
### ReThrow 활동 디자이너 사용  
 **Rethrow** 활동 디자이너는 **도구 상자**의 **오류 처리** 범주에 있습니다. 이 범주에 액세스하려면 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)]의 왼쪽에 있는 **도구 상자** 탭을 클릭하거나, **보기** 메뉴에서 **도구 모음**을 선택하거나, Ctrl\+Alt\+X를 누릅니다.  
  
 **도구 상자**의 **Rethrow** 활동 디자이너를 끌어다가 <xref:System.Activities.Statements.Sequence> 등 일반적으로 활동을 배치하는 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] 화면의 아무 곳에나 놓을 수 있습니다.그러면 기본 **DisplayName**인 Throw라는 이름의 <xref:System.Activities.Statements.Rethrow> 활동이 만들어집니다.**Rethrow** 활동 디자이너의 머리글 또는 속성 표의 **DisplayName** 상자에서 <xref:System.Activities.Activity.DisplayName%2A> 값을 편집할 수 있습니다.  
  
### Rethrow 속성  
 다음 표에서는 <xref:System.Activities.Statements.Rethrow> 속성을 보여 주고 디자이너에서 이 속성을 사용하는 방법을 설명합니다.  
  
|속성 이름|필수|사용법|  
|-----------|--------|---------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|<xref:System.Activities.Statements.ReThrow> 활동의 선택적 이름을 지정합니다.기본값은 Rethrow입니다.|  
  
## 참고 항목  
 [컬렉션](../workflow-designer/collection-activity-designers.md)   
 [Throw](../workflow-designer/throw-activity-designer.md)   
 [TryCatch](../workflow-designer/trycatch-activity-designer.md)