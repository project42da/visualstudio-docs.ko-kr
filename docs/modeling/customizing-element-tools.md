---
title: "요소 도구 사용자 지정 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6dac48b6-db68-4bcd-8aa2-422c2ad5d28b
caps.latest.revision: "6"
author: alancameronwills
ms.author: awills
manager: douge
ms.openlocfilehash: 2555fe2be42ed58482cdacf174a6cb035a8d7bd5
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="customizing-element-tools"></a>요소 도구 사용자 지정
일부 DSL 정의의 요소를 그룹으로 단일 개념을 나타냅니다. 예를 들어 구성 요소에는 고정된 포트 집합을 모델을 만들면 항상 하려는 경우 해당 부모 구성 요소와 같은 시간에 만들려는 포트. 따라서 하나가 아닌 요소의 그룹을 만듭니다 요소 작성 도구를 사용자 지정 해야 합니다. 이 위해 요소 작성 도구를 초기화 하는 방법을 사용자 지정할 수 있습니다.  
  
 다이어그램 또는 요소에 도구를 끌 때 수행 되는 작업을 재정의할 수 있습니다.  
  
## <a name="customizing-the-content-of-an-element-tool"></a>요소 도구의 콘텐츠를 사용자 지정  
 인스턴스를 저장 하는 각 요소 도구는 <xref:Microsoft.VisualStudio.Modeling.ElementGroupPrototype> 하나 이상의 모델 요소 및 링크의 직렬화 된 버전이 포함 된 (EGP). 기본적으로 요소 도구 EGP 도구에 대해 지정 하는 클래스의 인스턴스 하나를 포함 합니다. 재정의 하 여이 변경할 수 있습니다 *YourLanguage*`ToolboxHelper.CreateElementToolPrototype`합니다. 이 메서드는 DSL 패키지가 로드 될 때 호출 됩니다.  
  
 메서드의 매개 변수는 DSL 정의에 지정 하는 클래스의 ID입니다. 에 관심이 있는 클래스는 메서드를 호출 하는 경우에 EGP 추가 요소를 추가할 수 있습니다.  
  
 EGP 보조 요소에 대 한 기본 요소에서 링크를 포함을 포함 해야 합니다. 참조 링크를 포함할 수도 있습니다.  
  
 다음 예제에서는 기본 요소와 두 개의 포함 된 요소를 만듭니다. 주 클래스, 저항기 라고 되었으며 터미널 라는 요소에 두 개의 포함 관계. 포함 하는 역할 속성의 이름은 Terminal1 및 Terminal2, 및 둘 다 1.. 1 인의 복합성입니다.  
  
```  
using Microsoft.VisualStudio.Modeling; ...    
public partial class CircuitDiagramToolboxHelper  
{  
  protected override ElementGroupPrototype    CreateElementToolPrototype(Store store, Guid domainClassId)  
  {  
    // A case for each tool to customize:    
    if (domainClassId == Resistor.DomainClassId)  
    {  
      // Set up the prototype elements and links:  
      Resistor resistor = new Resistor(store);  
      resistor.Terminal1 = new Terminal(store);   
      resistor.Terminal2 = new Terminal(store);  
      resistor.Terminal1.Name = "T1"; // embedding  
      resistor.Terminal2.Name = "T2"; // embedding  
      // We could also set up reference links.  
  
      // Create an element group prototype for the toolbox:  
      ElementGroup egp = new ElementGroup(store.DefaultPartition);  
      egp.AddGraph(resistor, true);  
      // We do not have to explicitly include embedded children.  
      return egp.CreatePrototype();  
    }  
    // Element tools for other classes:  
    else  
      return base.CreateElementToolPrototype(store, domainClassId);  
  }  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [요소 만들기 및 이동 사용자 지정](../modeling/customizing-element-creation-and-movement.md)