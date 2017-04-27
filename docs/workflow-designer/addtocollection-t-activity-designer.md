---
title: "AddToCollection&lt;T&gt; 활동 디자이너 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "System.Activities.Statements.AddToCollection`1.UI"
ms.assetid: f7fc0702-164e-4370-8946-bb2f9f9384b7
caps.latest.revision: 5
author: "ErikRe"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# AddToCollection&lt;T&gt; 활동 디자이너
**AddToCollection\<T\>** 활동 디자이너는 <xref:System.Activities.Statements.AddToCollection%601> 활동을 만들고 구성하는 데 사용됩니다.  
  
## AddToCollection\<T\> 활동  
 <xref:System.Activities.Statements.AddToCollection%601> 활동은 컬렉션에 항목을 추가합니다.  
  
### AddToCollection\<T\> 활동 디자이너 사용  
 **AddToCollection\<T\>** 활동 디자이너는 **도구 상자**의 **컬렉션** 범주에 있습니다. 이 범주에 액세스하려면 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)]의 **도구 상자** 탭을 클릭하거나, **보기** 메뉴에서 **도구 모음**을 선택하거나, Ctrl\+Alt\+X를 누릅니다.  
  
 **도구 상자**의 **AddToCollection\<T\>** 활동 디자이너를 끌어다가 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] 화면의 <xref:System.Activities.Statements.Sequence> 등 일반적으로 활동을 배치하는 아무 곳에나 놓을 수 있습니다.그러면 기본 <xref:System.Activities.Activity.DisplayName%2A>인 AddToCollection\<Int32\>라는 이름의 <xref:System.Activities.Statements.AddToCollection%601> 활동이 만들어집니다.기본적으로 *TypeArgument*는 **Int32**입니다.속성 표에서 이를 변경할 수 있습니다. **AddToCollection\<T\>** 활동 디자이너의 머리글 또는 속성 표의 **DisplayName** 상자에서 <xref:System.Activities.Activity.DisplayName%2A> 값을 편집할 수 있습니다.다른 속성은 속성 표에서 편집해야 합니다.  
  
### AddToCollection\<T\> 속성  
 다음 표에서는 <xref:System.Activities.Statements.AddToCollection%601> 속성을 보여 주고 디자이너에서 이 속성을 사용하는 방법을 설명합니다.  
  
|속성 이름|필수|사용법|  
|-----------|--------|---------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|<xref:System.Activities.Statements.AddToCollection%601> 활동의 이름입니다.기본값은 AddToCollection\<Int32\>입니다.<xref:System.Activities.Activity.DisplayName%2A> 값은 꼭 필요하지 않더라도 사용하는 것이 좋습니다.|  
|<xref:System.Activities.Statements.AddToCollection%601.Item%2A>|True|Collection\<T\>에 추가할 항목입니다.이 항목의 형식 *T*는 *TypeArgument* 형식입니다.이 항목을 지정하려면 속성 표에 Visual Basic 식을 입력합니다.|  
|<xref:System.Activities.Statements.AddToCollection%601.Collection%2A>|True|항목이 추가될 컬렉션입니다.이 컬렉션은 **ICollection\<TypeArgument\>** 형식입니다.컬렉션을 지정하려면 속성 표에 Visual Basic 식을 입력합니다.|  
|*TypeArgument*|True|<xref:System.Collections.Generic.ICollection%601>에 포함된 항목의 형식 T입니다.기본적으로 이 *TypeArgument* 형식은 **Int32**로 설정됩니다.형식을 변경하려면 속성 표의 콤보 상자에서 *TypeArgument* 값을 변경합니다.|  
  
## 참고 항목  
 [컬렉션](../workflow-designer/collection-activity-designers.md)   
 [AddToCollection\<T\> Activity Designer](../workflow-designer/addtocollection-t-activity-designer.md)   
 [ClearCollection\<T\>](../workflow-designer/clearcollection-t-activity-designer.md)   
 [ExistsInCollection\<T\>](../workflow-designer/existsincollection-t-activity-designer.md)   
 [RemoveFromCollection\<T\>](../workflow-designer/removefromcollection-t-activity-designer.md)