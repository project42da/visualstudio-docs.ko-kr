---
title: "모양 및 연결선은 모델을 반영 하도록 업데이트 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 51eb2af9-00e7-4725-a87d-62fb4f39f444
caps.latest.revision: 6
author: alancameronwills
ms.author: awills
manager: douge
translationtype: Machine Translation
ms.sourcegitcommit: eb2ab9d49cdeb1ed71da8ef67841f7796862dc30
ms.openlocfilehash: 97ec749c0a89dae6c5a98702926d8ad82b6af3ac
ms.lasthandoff: 02/22/2017

---
# <a name="updating-shapes-and-connectors-to-reflect-the-model"></a>모양 및 연결선을 업데이트하여 모델 반영
도메인 관련 언어에서 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], 기본 모델의 상태를 반영 하는 도형의 모양을 만들 수 있습니다.  
  
 이 항목의 코드 예제에 추가할지는 `.cs` 파일에서 프로그램 `Dsl` 프로젝트. 각 파일에 이러한 문이 필요 합니다.  
  
```  
using Microsoft.VisualStudio.Modeling;  
using Microsoft.VisualStudio.Modeling.Diagrams;  
  
```  
  
## <a name="set-shape-map-properties-to-control-the-visibility-of-a-decorator"></a>모양 맵 속성을 설정 하는 데코레이터의 가시성 제어  
 DSL 정의에서 모양과 도메인 클래스 사이의 매핑을 구성 하 여 프로그램 코드를 작성 하지 않고도 데코레이터의 가시성을 제어할 수 있습니다. 자세한 내용은 참조  [도메인별 언어를 정의 하는 방법을](../modeling/how-to-define-a-domain-specific-language.md)합니다.
  
## <a name="expose-the-color-and-style-of-a-shape-as-properties"></a>색상 및 모양의 스타일 속성으로 노출  
 DSL 정의에서 shape 클래스를 마우스 오른쪽 **Add Exposed**, 다음 항목 중 하나를 같은 클릭 하 고 **채우기 색**합니다.  
  
 모양 또는 사용자는 프로그램 코드에서 설정할 수 있는 도메인 속성을 설정 되었습니다. 예를 들어, 명령 또는 규칙의 프로그램 코드에서 설정를 작성할 수 있습니다.  
  
 `shape.FillColor = System.Drawing.Color.Red;`  
  
 사용자가 아닌 경우에 프로그램 제어 속성 변수를 확인 하려는 경우 새 도메인 속성을 같은 선택 **채우기 색** DSL 정의 다이어그램에서. 그런 다음 속성 창에서 설정 **Is Browsable** 를 `false` 설정 또는 **UI Readonly가** 를 `true`합니다.  
  
## <a name="define-change-rules-to-make-color-style-or-location-depend-on-model-element-properties"></a>색, 스타일 또는 모델 요소 속성에 종속 되는 위치를 확인 하는 변경 규칙 정의  
 모델의 다른 부분에 종속 된 도형 모양을 업데이트 하는 규칙을 정의할 수 있습니다. 예를 들어 모델 요소의 속성에 종속 된 셰이프의 색을 업데이트 하는 모델 요소에 대해 변경 규칙을 정의할 수 있습니다. 변경 규칙에 대 한 자세한 내용은 참조 [규칙 전파 변경 내에서 모델](../modeling/rules-propagate-changes-within-the-model.md)합니다.  
  
 규칙 실행 취소 명령을 수행 될 때 호출 되지 않습니다 때문에 저장소 내에서 유지 관리 되는 속성을 업데이트에 규칙을 사용 해야 합니다. 여기에 크기 및 모양의 표시 여부와 같은 일부 그래픽 기능 포함 되지 않습니다. 도형의 이러한 기능을 업데이트 하려면 참조 [아닌 저장소 그래픽 업데이트 기능](#OnAssociatedProperty)합니다.  
  
 다음 예제에서는 노출 했다고 가정 `FillColor` 이전 섹션에 설명 된 대로 도메인 속성으로.  
  
```c#  
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
  
## <a name="use-onchildconfigured-to-initialize-a-shapes-properties"></a>OnChildConfigured를 사용 하 여 셰이프의 속성을 초기화 하려면  
 처음 셰이프의 속성을 설정 하려면 재정의 만든는 `OnChildConfigured()` 다이어그램 클래스의 부분 정의에 있습니다. 다이어그램 클래스는 DSL 정의에 지정 되 고 생성 된 코드는 **Dsl\Generated Code\Diagram.cs**합니다. 예:  
  
```c#  
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
  
 이 메서드는 모두 도메인 속성 및 도형의 크기와 같은 비 스토어 기능에 대해 사용할 수 있습니다.  
  
##  <a name="a-nameonassociatedpropertya-use-associatevaluewith-to-update-other-features-of-a-shape"></a><a name="OnAssociatedProperty"></a>AssociateValueWith()를 사용 하 여 도형의 다른 기능을 업데이트 하려면  
 그림자, 또는 연결선의 화살표 스타일에 있는지 여부와 같은 모양의 일부 기능에 대 한 노출 하는 기능을 도메인 속성의 기본 설정 방법이 있습니다.  이러한 기능에는 변경 트랜잭션 시스템에서 제어 하지 않습니다. 따라서 업데이트 하는 데 적합 하지 않음을 규칙은 사용자가 실행 취소 명령을 수행 하는 경우를 호출 되지 않으므로 규칙을 사용 합니다.  
  
 대신, <xref:Microsoft.VisualStudio.Modeling.Diagrams.ShapeElement.OnAssociatedPropertyChanged%2A>.</xref:Microsoft.VisualStudio.Modeling.Diagrams.ShapeElement.OnAssociatedPropertyChanged%2A> 를 사용 하 여 이러한 기능을 업데이트할 수 있습니다. 다음 예제에서는 연결선의 화살표 스타일은 커넥터를 표시 하는 관계의 도메인 속성의 값으로 제어 됩니다.  
  
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
        { // Update the shape’s built-in Decorator feature:  
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
  
 `AssociateValueWith()`등록 하려는 각 도메인 속성에 대해 한 번씩을 호출 되어야 합니다. 지정된 된 속성에 변경 내용을 호출 호출 된 후 `OnAssociatedPropertyChanged()` 속성의 모델 요소를 제공 하는 모든 셰이프에 있습니다.  
  
 호출할 필요가 없는 `AssociateValueWith()` 각 인스턴스에 대 한 합니다. InitializeResources 인스턴스 메서드 이면 있지만 각 shape 클래스에 대해 한 번만 호출 됩니다.
