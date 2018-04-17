---
title: 색, 선 스타일 및 기타 모양 속성을 제어 합니다. | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: e49e6cbc6ecfba85e2c2684b0a7e71e05757ab59
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="controlling-color-line-style-and-other-shape-properties"></a>색, 선 스타일 및 기타 모양 속성 제어
일부 셰이프 속성 색 노출 될 수 있습니다' '-같은 즉, 연결 된 셰이프의 도메인 속성에 합니다. 일부는에 대 한 직접 제어 합니다.  
  
## <a name="exposing-a-property"></a>속성을 노출합니다.  
 색과 같은 일부 셰이프 속성 도메인 속성의 값에 연결할 수 있습니다.  
  
 DSL 정의 도형, 커넥터 또는 다이어그램 클래스를 선택 합니다. 해당 상황에 맞는 메뉴에서 선택 **노출 추가**를 채우기 색 등의 원하는 속성을 선택 합니다.  
  
 모양에는 이제 프로그램 코드에서 또는 사용자로 설정할 수 있는 도메인 속성을 있습니다.  
  
## <a name="dynamically-updating-an-exposed-property"></a>노출 된 속성을 동적으로 업데이트합니다.  
 일반적으로 다른 속성에 따라 노출 된 속성을 확인 하려고 합니다. 예를 들어 좋습니다 0 보다 작은 있는 셰이프를 특정 도메인 속성은 때마다 빨간색으로 바뀝니다. 이 종속성을 하려면 만들고는 [규칙](../modeling/rules-propagate-changes-within-the-model.md)합니다. 예를 들어:  
  
```csharp  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using Microsoft.VisualStudio.Modeling;  
using Microsoft.VisualStudio.Modeling.Diagrams;  
namespace ExampleNamespace  
{  
 // Attribute associates the rule with class:  
 [RuleOn(typeof(CarShape), FireTime = TimeToFire.TopLevelCommit)]  
 // The rule is a class derived from one of the abstract rules:  
 class CarShapeAddRule : AddRule  
 {  
 // Override the abstract method:  
 public override void ElementAdded(ElementAddedEventArgs e)  
 {  
 base.ElementAdded(e);  
 CarShape shape = e.ModelElement as CarShape;  
 Store store = shape.Store;  
 // Ignore this call if we're currently loading a model:  
 if (store.TransactionManager.CurrentTransaction.IsSerializing)   
  return;  
 Car car = shape.ModelElement as Car;  
 // Code here propagates change as required - for example:  
 shape.FillColor = car.Somebool ? System.Drawing.Color.Red : System.Drawing.Color.Green;   
 }  
}  
 // The rule must be registered:  
 public partial class ExampleDomainModel  
 {  
 protected override Type[] GetCustomDomainModelTypes()  
 {  
  List<Type> types = new List<Type>(base.GetCustomDomainModelTypes());  
  types.Add(typeof(CarShapeAddRule));  
  // If you add more rules, list them here.   
  return types.ToArray();  
 }  
 }  
}  
```