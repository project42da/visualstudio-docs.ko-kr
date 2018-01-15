---
title: "셰이프 및 연결선은 모델을 반영 하도록 업데이트 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 2f192b1bc65d9040ea6ae4fa1278e053398425c7
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/13/2018
---
# <a name="updating-shapes-and-connectors-to-reflect-the-model"></a>모양 및 연결선을 업데이트하여 모델 반영
에 도메인 특정 언어 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], 기본 모델의 상태를 반영 하는 도형의 모양을 만들 수 있습니다.  
  
 이 항목의 코드 예제에 추가할지는 `.cs` 파일 프로그램 `Dsl` 프로젝트. 각 파일에 이러한 문이 필요 합니다.  
  
```  
using Microsoft.VisualStudio.Modeling;  
using Microsoft.VisualStudio.Modeling.Diagrams;  
  
```  
  
## <a name="set-shape-map-properties-to-control-the-visibility-of-a-decorator"></a>도형 맵 속성을 설정 하는 데코레이터의 표시 유형을 제어합니다  
 DSL 정의에서 모양과 도메인 클래스 간의 매핑을 구성 하 여 프로그램 코드를 작성 하지 않고도 데코레이터의 표시 여부를 제어할 수 있습니다. 자세한 내용은 참조 [도메인 특정 언어를 정의 하는 방법을](../modeling/how-to-define-a-domain-specific-language.md)합니다.
  
## <a name="expose-the-color-and-style-of-a-shape-as-properties"></a>색 및 스타일 도형의 속성으로 노출  
 DSL 정의에 단추로 shape 클래스 **노출 추가**, 다음 항목 중 하나를 같은 클릭 하 고 **채우기 색**합니다.  
  
 모양에는 이제 프로그램 코드에서 또는 사용자로 설정할 수 있는 도메인 속성을 있습니다. 예를 들어, 명령 또는 규칙의 프로그램 코드에 설정를 작성할 수 있습니다.  
  
 `shape.FillColor = System.Drawing.Color.Red;`  
  
 프로그램 제어만 하 고 사용자가 아니라 속성 변수를 확인 하려는 경우 새 도메인 속성을 같은 선택 **채우기 색** DSL 정의 다이어그램에 있습니다. 그런 다음 속성 창에서 설정 **는 검색 가능한** 를 `false` 설정 또는 **UI Readonly가** 를 `true`합니다.  
  
## <a name="define-change-rules-to-make-color-style-or-location-depend-on-model-element-properties"></a>색, 스타일 또는 모델 요소 속성에 종속 되는 위치를 변경 규칙 정의  
 모양 모델의 다른 부분에 종속 셰이프를 업데이트 하는 규칙을 정의할 수 있습니다. 예를 들어 모델 요소의 속성에 종속 된 셰이프의 색을 업데이트 하는 모델 요소에 대해 변경 규칙을 정의할 수 있습니다. 변경 규칙에 대 한 자세한 내용은 참조 [규칙 전파 변경 내에서 모델](../modeling/rules-propagate-changes-within-the-model.md)합니다.  
  
 규칙 실행 취소 명령을 수행 될 때 호출 되지 않습니다 때문에 저장소를 내에서 유지 관리 되는 속성을 업데이트에 규칙을 사용 해야 합니다. 크기와 셰이프의 표시 여부와 같은 일부 그래픽 기능은 다루지 않습니다. 도형의 이러한 기능을 업데이트 하려면 참조 [비 저장소 그래픽 업데이트 기능](#OnAssociatedProperty)합니다.  
  
 다음 예에서는 노출 했다고 가정 `FillColor` 이전 섹션에 설명 된 대로 도메인 속성으로.  
  
```csharp  
[RuleOn(typeof(ExampleElement))]  
  class ExampleElementPropertyRule : ChangeRule  
  {  
    public override void ElementPropertyChanged(ElementPropertyChangedEventArgs e)  
    {  
      base.ElementPropertyChanged(e);  
      ExampleElement element = e.ModelElement as ExampleElement;  
      // The rule is called for every property that is updated.  
      // Therefore, verify which property changed:  
      if (e.DomainProperty.Id == ExampleElement.NameDomainPropertyId)  
      {  
        // There is usually only one shape:  
        foreach (PresentationElement pel in PresentationViewsSubject.GetPresentation(element))  
        {  
          ExampleShape shape = pel as ExampleShape;  
          // Replace this with a useful condition:  
          shape.FillColor = element.Name.EndsWith("3")   
                     ? System.Drawing.Color.Red : System.Drawing.Color.Green;  
        }  
      }  
    }  
  }  
  // The rule must be registered:  
  public partial class OnAssociatedPropertyExptDomainModel  
  {  
    protected override Type[] GetCustomDomainModelTypes()  
    {  
      List<Type> types = new List<Type>(base.GetCustomDomainModelTypes());  
      types.Add(typeof(ExampleElementPropertyRule));  
      // If you add more rules, list them here.   
      return types.ToArray();  
    }  
  }  
  
```  
  
## <a name="use-onchildconfigured-to-initialize-a-shapes-properties"></a>OnChildConfigured 셰이프의 속성을 초기화 사용  
 처음 셰이프의 속성을 설정 하려면 만들어지면 재정의 `OnChildConfigured()` 다이어그램 클래스의 부분 정의에서 합니다. DSL 정의에 다이어그램 클래스를 지정 하 고 생성 된 코드는 **Dsl\Generated Code\Diagram.cs**합니다. 예:  
  
```csharp  
partial class MyLanguageDiagram  
{  
  protected override void OnChildConfigured(ShapeElement child, bool childWasPlaced, bool createdDuringViewFixup)  
  {  
    base.OnChildConfigured(child, childWasPlaced, createdDuringViewFixup);  
    ExampleShape shape = child as ExampleShape;  
    if (shape != null)   
    {  
      if (!createdDuringViewFixup) return; // Ignore load from file.  
      ExampleElement element = shape.ModelElement as ExampleElement;  
      // Replace with a useful condition:  
      shape.FillColor = element.Name.EndsWith("3")   
          ? System.Drawing.Color.Red : System.Drawing.Color.Green;  
    }  
    // else deal with other types of shapes and connectors.  
  }  
}  
  
```  
  
 이 메서드는 모두 도메인 속성 및 도형의 크기와 같은 비 저장소 기능을 사용할 수 있습니다.  
  
##  <a name="OnAssociatedProperty"></a>AssociateValueWith()를 사용 하 여 도형의 다른 기능을 업데이트 하려면  
 그림자를 또는 연결선의 화살표 스타일에 있는지 여부 등의 셰이프의 일부 기능에 대 한 기능 도메인 속성으로 노출 기본 설정 방법이 있습니다.  등의 기능이 변경 내용은 트랜잭션 시스템에 의해 제어 되지 않습니다. 따라서 해당 키를 업데이트 하는 데 적합 하지 않음을 규칙을를 사용 하는 실행 취소 명령을 수행할 때 규칙 호출 되지 않습니다.  
  
 대신, 사용 하 여 이러한 기능을 업데이트할 수 있습니다 <xref:Microsoft.VisualStudio.Modeling.Diagrams.ShapeElement.OnAssociatedPropertyChanged%2A>합니다. 다음 예제에서는 연결선의 화살표 스타일은 커넥터를 표시 하는 관계의 domain 속성 값에 의해 제어 됩니다.  
  
```  
public partial class ArrowConnector // My connector class.   
{  
   /// <summary>  
    /// Called whenever a registered property changes in the associated model element.  
    /// </summary>  
    /// <param name="e"></param>  
    protected override void OnAssociatedPropertyChanged(VisualStudio.Modeling.Diagrams.PropertyChangedEventArgs e)  
    {  
      base.OnAssociatedPropertyChanged(e);  
      // Can be called for any property change. Therefore,  
      // Verify that this is the property we're interested in:  
      if ("IsDirected".Equals(e.PropertyName))  
      {  
        if (e.NewValue.Equals(true))  
        { // Update the shape's built-in Decorator feature:  
          this.DecoratorTo = LinkDecorator.DecoratorEmptyArrow;  
        }  
        else  
        {  
          this.DecoratorTo = null; // No arrowhead.  
        }  
      }  
    }  
    // OnAssociatedPropertyChanged is called only for properties  
    // that have been registered using AssociateValueWith().  
    // InitializeResources is a convenient place to call this.  
    // This method is invoked only once per class, even though  
    // it is an instance method.   
    protected override void InitializeResources(StyleSet classStyleSet)  
    {  
      base.InitializeResources(classStyleSet);  
      AssociateValueWith(this.Store, Wire.IsDirectedDomainPropertyId);  
      // Add other properties here.  
    }  
}  
  
```  
  
 `AssociateValueWith()`등록 하려는 각 도메인 속성에 대해 한 번씩을 호출 되어야 합니다. 지정된 된 속성을 변경한 호출 호출 된 후 `OnAssociatedPropertyChanged()` 속성의 모델 요소를 제공 하는 모든 셰이프에 있습니다.  
  
 호출할 필요는 없습니다 `AssociateValueWith()` 각 인스턴스에 대 한 합니다. InitializeResources 인스턴스 메서드인 경우에 각 셰이프 클래스에 대해 한 번만 호출 됩니다.
