---
title: "TryCatch 활동 디자이너 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "System.Activities.Statements.TryCatch.UI"
  - "System.Activities.Statements.Catch`1.UI"
ms.assetid: 02a326c2-4009-442f-b7cb-e42121fd2992
caps.latest.revision: 8
caps.handback.revision: 8
author: "ErikRe"
ms.author: "erikre"
manager: "erikre"
---
# TryCatch 활동 디자이너
**TrayCatch** 활동 디자이너는 <xref:System.Activities.Statements.TryCatch> 활동을 만들고 구성하는 데 사용됩니다.  
  
## TryCatch 활동  
 <xref:System.Activities.Statements.TryCatch> 활동에는 **Catch\<TException\>**<xref:System.Activities.Statements.TryCatch.Try%2A> 및 <xref:System.Activities.Statements.TryCatch.Finally%2A> 활동의 컬렉션인  활동이 포함됩니다.**TException** 형식의 <xref:System.Activities.Statements.Catch%601>에는 <xref:System.Activities.Statements.Catch%601.ExceptionType%2A> 및 <xref:System.Activities.Statements.Catch%601.Action%2A>이 포함됩니다.둘 다 일반적인 예외 기반의 오류 처리 메커니즘을 구현하는 데 사용됩니다.<xref:System.Activities.Statements.TryCatch> 활동은 <xref:System.Activities.Statements.TryCatch.Try%2A> 활동을 실행하려고 합니다.<xref:System.Activities.Statements.TryCatch.Try%2A> 활동이 예외를 throw하는 경우 <xref:System.Activities.Statements.TryCatch> 활동은 **Catch\<TException\>** 컬렉션을 사용하여 예외의 일치 항목을 찾습니다.일치하는 항목이 있으면 해당 **Catch\<TException\>**의 <xref:System.Activities.Statements.Catch%601.Action%2A>이 실행되어 예외에 대한 오류 처리 논리로 사용됩니다.<xref:System.Activities.Statements.TryCatch.Try%2A> 섹션의 활동이 성공적으로 완료되었거나 <xref:System.Activities.Statements.TryCatch.Catches%2A>의 활동이 성공적으로 완료된 경우 <xref:System.Activities.Statements.TryCatch> 활동은 해당 <xref:System.Activities.Statements.TryCatch.Finally%2A> 활동을 실행합니다.[!INCLUDE[crdefault](../test/includes/crdefault_md.md)][예외](../Topic/Exceptions.md).  
  
### TryCatch 활동 디자이너 사용  
 **TryCatch** 활동 디자이너는 **도구 상자**의 **오류 처리** 범주에 있습니다. 이 범주에 액세스하려면 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] 왼쪽의 **도구 상자** 탭을 클릭하거나, **보기** 메뉴에서 **도구 모음**을 선택하거나, Ctrl\+Alt\+X를 누릅니다.  
  
 **TryCatch** 활동 디자이너를 **도구 상자**에서 끌어다가 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] 화면의 <xref:System.Activities.Statements.Sequence> 등 일반적으로 활동을 배치하는 곳에 놓을 수 있습니다.이렇게 하면 기본 <xref:System.Activities.Activity.DisplayName%2A>인 TryCatch라는 이름의 <xref:System.Activities.Statements.TryCatch> 활동이 만들어집니다.**TryCatch** 활동 디자이너의 머리글 또는 속성 표의 **DisplayName** 상자에서 <xref:System.Activities.Activity.DisplayName%2A> 값을 편집할 수 있습니다.다른 속성은 **TryCatch** 활동 디자이너의 화면에서 편집해야 합니다.  
  
 **TryCatch** 디자이너의 오른쪽 위 모서리에 있는 확장 단추를 클릭하여 확장된 보기에 **Try**, **Catch** 및 **Finally** 상자를 표시합니다.Catch를 추가하려면 **TryCatch** 디자이너에서 **새 Catch 추가** 단추를 클릭합니다.단추가 형식 콤보 상자로 바뀝니다.예외 형식을 선택하고 &lt;ENTER&gt; 키를 눌러 Catch를 추가합니다.**Catch**를 추가하면 Catch 영역이 확장되고 활동을 Catch로 끌어 놓아 해당 Catch의 실행 논리를 정의할 수 있습니다.확장된 Catch 영역 오른쪽에는 텍스트 상자가 있습니다.이 텍스트 상자를 사용하여 예외 변수의 이름을 지정할 수 있습니다.예외 변수는 동일한 **Catch** 내의 활동에만 사용할 수 있습니다.  
  
 **TryCatch** 디자이너는 **Catch** 편집을 지원하지 않습니다.예외 형식을 변경하려면 **Catch**를 삭제한 후 새 Catch를 추가해야 합니다.**Catch**를 선택하고 삭제하거나 마우스 오른쪽 단추를 클릭한 다음 상황에 맞는 메뉴의 **삭제** 메뉴를 사용하여 Catch를 삭제할 수 있습니다.  
  
### TryCatch 속성  
 다음 표에서는 <xref:System.Activities.Statements.TryCatch> 속성을 보여 주고 디자이너에서 이 속성을 사용하는 방법을 설명합니다.  
  
|속성 이름|필수|사용법|  
|-----------|--------|---------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|<xref:System.Activities.Statements.TryCatch> 활동의 선택적 이름을 지정합니다.기본 TryCatch입니다.|  
|<xref:System.Activities.Statements.TryCatch.Try%2A>|False|<xref:System.Activities.Statements.TryCatch>를 실행할 때 먼저 실행된 활동입니다.|  
|<xref:System.Activities.Statements.TryCatch.Catches%2A>|False|<xref:System.Activities.Statements.TryCatch.Try%2A> 활동이 예외를 throw할 때 확인해야 할 **Catch** 요소의 컬렉션입니다.<br /><br /> <xref:System.Activities.Statements.TryCatch.Catches%2A>에 하나 이상의 활동을 추가하거나 <xref:System.Activities.Statements.TryCatch.Finally%2A> 블록에 활동을 추가해야 합니다.|  
|<xref:System.Activities.Statements.TryCatch.Finally%2A>|False|<xref:System.Activities.Statements.TryCatch.Try%2A> 및 <xref:System.Activities.Statements.TryCatch.Catches%2A> 컬렉션의 필요한 모든 활동이 실행 완료될 때 실행할 활동입니다.<br /><br /> <xref:System.Activities.Statements.TryCatch.Catches%2A>에 하나 이상의 활동을 추가하거나 <xref:System.Activities.Statements.TryCatch.Finally%2A> 블록에 활동을 추가해야 합니다.|  
  
## 참고 항목  
 [컬렉션](../workflow-designer/collection-activity-designers.md)   
 [Rethrow](../workflow-designer/rethrow-activity-designer.md)   
 [Throw](../workflow-designer/throw-activity-designer.md)