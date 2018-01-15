---
title: "방법: 도형 또는 Decorator 클릭 가로채기 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Domain-Specific Language, programming domain models
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 3bb463fb8f6a668a082f5f1852673a387a4cd720
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/13/2018
---
# <a name="how-to-intercept-a-click-on-a-shape-or-decorator"></a>방법: 모양 또는 데코레이터 클릭 가로채기
다음 절차는 셰이프나 아이콘 decorator 클릭 가로채기 하는 방법을 보여 줍니다. 번의 클릭을 가로챌 수, 두 번 클릭할 끌기과 기타 제스처, 응답 요소를 확인 합니다.  
  
## <a name="to-intercept-clicks-on-shapes"></a>도형에 대 한 클릭을 가로챌 수  
 Dsl 프로젝트 생성 된 코드 파일에서 별도 코드 파일에서 shape 클래스에 대 한 partial 클래스 정의 작성 합니다. 재정의 `OnDoubleClick()` 문자로 시작 하는 이름을 가진 다른 방법 중 하나 또는 `On...`합니다. 예:  
  
```  
public partial class MyShape // change  
  {  
    public override void OnDoubleClick(DiagramPointEventArgs e)  
    {  
      base.OnDoubleClick(e);  
      System.Windows.Forms.MessageBox.Show("Click");  
      e.Handled = true;  
  }  }  
```  
  
> [!NOTE]
>  설정 `e.Handled` 를 `true`이벤트를 포함 하는 모양 또는 다이어그램에 전달 하지 않는 한, 합니다.  
  
## <a name="to-intercept-clicks-on-decorators"></a>데코레이터에 대 한 클릭을 가로챌 수  
 이미지 데코레이터 OnDoubleClick 메서드가 들어 있는 ImageField 클래스의 인스턴스에서 수행 됩니다. ImageField 서브 클래스를 작성 하는 경우의 클릭을 가로챌 수 있습니다. 필드는 InitializeShapeFields 메서드에서 설정 됩니다. 따라서 해당 방법을 대신 일반 ImageField 서브 클래스를 인스턴스화할 수를 변경 해야 합니다. InitializeShapeFields 방법은 shape 클래스의 생성된 된 코드에 있습니다. 설정 하는 경우에 shape 클래스를 재정의할 수는 `Generates Double Derived` 다음 절차에 설명 된 대로 속성입니다.  
  
 InitializeShapeFields 인스턴스 메서드인 경우에 각 클래스에 대해 한 번만 호출 됩니다. 따라서, 다이어그램의 각 셰이프에 대해 하나의 인스턴스가 아닌 각 클래스의 각 필드에 대 한 ClickableImageField의 인스턴스가 하나만 존재합니다. 사용자가 인스턴스를 식별 해야 인스턴스 적중 된 예제에서 코드에서 보여 주듯이 합니다.  
  
#### <a name="to-intercept-a-click-on-an-icon-decorator"></a>아이콘 decorator 클릭 가로채기를  
  
1.  열거나 DSL 솔루션을 만듭니다.  
  
2.  선택 하 고 또는 포함 된 아이콘 decorator 셰이프를 만들고 도메인 클래스에 매핑하십시오.  
  
3.  에 있는 파일에서 별도 코드 파일에는 `GeneratedCode` 폴더를 이미지 필드의 새 하위 클래스를 만듭니다.  
  
    ```  
    using Microsoft.VisualStudio.Modeling;  
    using Microsoft.VisualStudio.Modeling.Design;  
    using Microsoft.VisualStudio.Modeling.Diagrams;  
    using System.Collections.Generic;  
    using System.Linq;  
  
    namespace Fabrikam.MyDsl { // Change to your namespace  
    internal class ClickableImageField : ImageField  
    {  
      // You can also override OnClick and so on.  
      public override void OnDoubleClick(DiagramPointEventArgs e)  
      {  
        base.OnDoubleClick(e);  
        // Work out which instance was hit.  
        MyShape shapeHit = e.HitDiagramItem.Shape as MyShape;  
        if (shapeHit != null)  
        {  
          MyDomainClass element =   
              shapeHit.ModelElement as MyDomainClass;  
          System.Windows.Forms.MessageBox.Show(  
             "Double click on shape for " + element.Name);  
          // If we do not set Handled, the event will  
          // be passed to the containing shape:  
          e.Handled = true;  
        }  
      }  
  
       public ClickableImageField(string fieldName)  
         : base(fieldName)  
       { }  
    }  
    ```  
  
     Handled 상위 셰이프를 전달 하도록 이벤트를 원하지 않는 경우 true로 설정 해야 합니다.  
  
4.  다음 부분 클래스 정의 추가 하 여 도형 classs에서 InitializeShapeFields 메서드를 재정의 합니다.  
  
    ```  
    public partial class MyShape // change  
    {  
     protected override void InitializeShapeFields  
          (IList<ShapeField> shapeFields)  
     {  
      base.InitializeShapeFields(shapeFields);  
      // You can see the above method in MyShapeBase   
      // in the generated Shapes.cs  
      // It has already added fields for the Icons.  
      // So you will have to retrieve them and replace with your own.  
      ShapeField unwantedField = shapeFields.First  
          (field => field.Name == "IconDecorator1");  
      shapeFields.Remove(unwantedField);  
  
      // Now replicate the generated code from the base class   
      // in Shape.cs, but with your own image constructor.  
      ImageField field2 = new ClickableImageField("IconDecorator1");        
      field2.DefaultImage = ImageHelper.GetImage(  
        MyDslDomainModel.SingletonResourceManager  
        .GetObject("MyShapeIconDecorator1DefaultImage"));  
          shapeFields.Add(field2);  
    }  
    ```  
  
1.  솔루션을 빌드하고 실행합니다.  
  
2.  도형의 인스턴스에서 아이콘을 두 번 클릭 합니다. 테스트 메시지를 표시 됩니다.  
  
## <a name="intercepting-clicks-and-drags-on-compartmentshape-lists"></a>가로채 클릭 하 고 끌어서 CompartmentShape 목록에  
 다음 샘플에서는 구획 모양에 항목을 끌어서 순서 수 있습니다. 이 코드를 실행 합니다.  
  
1.  사용 하 여 새 DSL 솔루션을 만듭니다는 **클래스 다이어그램** 솔루션 템플릿을 합니다.  
  
     자신만의 구획 셰이프를 포함 하는 솔루션을 작업할 수도 있습니다. 이 코드는 도형 나타내는 모델 요소와 구획 목록 항목에 표시 된 요소 간의 포함 관계를 가정 합니다.  
  
2.  설정의 **Double 파생 생성** 구획 셰이프의 속성입니다.  
  
3.  이 코드 파일에 추가 된 **Dsl** 프로젝트.  
  
4.  고유한 DSL 일치 하도록이 코드의 도메인 클래스 및 모양 이름을 조정 합니다.  
  
 요약 하자면, 코드는 다음과 같이 작동합니다. 이 예제에서는 `ClassShape` 구획 모양 이름입니다.  
  
-   마우스 이벤트 처리기의 집합을 만들 때 각 구획 인스턴스에 연결 됩니다.  
  
-   `ClassShape.MouseDown` 현재 항목을 저장 하는 이벤트입니다.  
  
-   마우스 이동 하면 현재 항목에서 MouseAction 인스턴스의 만든 커서를 설정 하 고 해제 될 때까지 마우스를 캡처할 합니다.  
  
     항목의 텍스트를 선택 하는 등의 다른 마우스 작업에 방해가 되지 않도록 하려면 MouseAction는 원래 항목 마우스가 될 때까지 생성 되지 않습니다.  
  
     MouseUp 수신 대기 하는 MouseAction 만드는 대신 단순히 것입니다. 그러나이 제대로 작동 하지 구획 외부 끌어 놓은 후 마우스를 놓을 경우. MouseAction는 마우스를 해제 하는 위치에 관계 없이 적절 한 조치를 수행할 수 있습니다.  
  
-   마우스를 놓으면 MouseAction.MouseUp 모델 요소 간 링크의 순서를 재정렬 합니다.  
  
-   역할 순서를 변경 하 여 화면을 업데이트 하는 규칙을 발생 시킵니다. 이 문제를 이미 정의 되며 추가 코드 없이 필요 합니다.  
  
```csharp  
using Microsoft.VisualStudio.Modeling;  
using Microsoft.VisualStudio.Modeling.Design;  
using Microsoft.VisualStudio.Modeling.Diagrams;  
using System.Collections.Generic;  
using System.Linq;  
  
// This sample allows users to re-order items in a compartment shape by dragging.  
  
// This example is built on the "Class Diagrams" solution template of VMSDK (DSL Tools).  
// You will need to change the following domain class names to your own:  
// ClassShape = a compartment shape  
// ClassModelElement = the domain class displayed using a ClassShape  
// This code assumes that the embedding relationships   
// displayed in the compartments don't use inheritance   
// (don't have base or derived domain relationships).  
  
namespace Company.CompartmentDrag  
{  
 /// <summary>  
 /// Manage the mouse while dragging a compartment item.  
 /// </summary>  
 public class CompartmentDragMouseAction : MouseAction  
 {  
  private ModelElement sourceChild;  
  private ClassShape sourceShape;  
  private RectangleD sourceCompartmentBounds;  
  
  public CompartmentDragMouseAction(ModelElement sourceChildElement, ClassShape sourceParentShape, RectangleD bounds)  
   : base (sourceParentShape.Diagram)  
  {  
   sourceChild = sourceChildElement;  
   sourceShape = sourceParentShape;  
   sourceCompartmentBounds = bounds; // For cursor.  
  }  
  
  /// <summary>  
  /// Call back to the source shape to drop the dragged item.  
  /// </summary>  
  /// <param name="e"></param>  
  protected override void OnMouseUp(DiagramMouseEventArgs e)  
  {  
   base.OnMouseUp(e);  
   sourceShape.DoMouseUp(sourceChild, e);  
   this.Cancel(e.DiagramClientView);  
   e.Handled = true;  
  }  
  
  /// <summary>  
  /// Ideally, this shouldn't happen. This action should only be active  
  /// while the mouse is still pressed. However, it can happen if you  
  /// move the mouse rapidly out of the source shape, let go, and then   
  /// click somewhere else in the source shape.  
  /// </summary>  
  /// <param name="e"></param>  
  protected override void OnMouseDown(DiagramMouseEventArgs e)  
  {  
   base.OnMouseDown(e);  
   this.Cancel(e.DiagramClientView);  
   e.Handled = false;  
  }  
  
  /// <summary>  
  /// Display an appropriate cursor while the drag is in progress:  
  /// Up-down arrow if we are inside the original compartment.  
  /// No entry if we are elsewhere.  
  /// </summary>  
  /// <param name="currentCursor"></param>  
  /// <param name="diagramClientView"></param>  
  /// <param name="mousePosition"></param>  
  /// <returns></returns>  
  public override System.Windows.Forms.Cursor GetCursor(System.Windows.Forms.Cursor currentCursor, DiagramClientView diagramClientView, PointD mousePosition)  
  {  
   // If the cursor is inside the original compartment, show up-down cursor.  
   return sourceCompartmentBounds.Contains(mousePosition)   
    ? System.Windows.Forms.Cursors.SizeNS // Up-down arrow.  
    : System.Windows.Forms.Cursors.No;  
  }  
 }  
  
 /// <summary>  
 /// Override some methods of the compartment shape.  
 /// *** GenerateDoubleDerived must be set for this shape in DslDefinition.dsl. ****  
 /// </summary>  
 public partial class ClassShape  
 {  
  /// <summary>  
  /// Model element that is being dragged.  
  /// </summary>  
  private static ClassModelElement dragStartElement = null;  
  /// <summary>  
  /// Absolute bounds of the compartment, used to set the cursor.  
  /// </summary>  
  private static RectangleD compartmentBounds;  
  
  /// <summary>  
  /// Attach mouse listeners to the compartments for the shape.  
  /// This is called once per compartment shape.  
  /// The base method creates the compartments for this shape.  
  /// </summary>  
  public override void EnsureCompartments()  
  {  
   base.EnsureCompartments();  
   foreach (Compartment compartment in this.NestedChildShapes.OfType<Compartment>())  
   {  
    compartment.MouseDown += new DiagramMouseEventHandler(compartment_MouseDown);  
    compartment.MouseUp += new DiagramMouseEventHandler(compartment_MouseUp);  
    compartment.MouseMove += new DiagramMouseEventHandler(compartment_MouseMove);  
   }  
  }  
  
  /// <summary>  
  /// Remember which item the mouse was dragged from.  
  /// We don't create an Action immediately, as this would inhibit the  
  /// inline text editing feature. Instead, we just remember the details  
  /// and will create an Action when/if the mouse moves off this list item.  
  /// </summary>  
  /// <param name="sender"></param>  
  /// <param name="e"></param>  
  void compartment_MouseDown(object sender, DiagramMouseEventArgs e)  
  {  
   dragStartElement = e.HitDiagramItem.RepresentedElements  
     .OfType<ClassModelElement>().FirstOrDefault();  
   compartmentBounds = e.HitDiagramItem.Shape.AbsoluteBoundingBox;  
  }  
  
  /// <summary>  
  /// When the mouse moves away from the initial list item,  
  /// but still inside the compartment, create an Action   
  /// to supervise the cursor and handle subsequent mouse events.  
  /// Transfer the details of the initial mouse position to the Action.  
  /// </summary>  
  /// <param name="sender"></param>  
  /// <param name="e"></param>  
  void compartment_MouseMove(object sender, DiagramMouseEventArgs e)  
  {  
   if (dragStartElement != null)  
   {  
    if (dragStartElement != e.HitDiagramItem.RepresentedElements.OfType<ClassModelElement>().FirstOrDefault())  
    {  
     e.DiagramClientView.ActiveMouseAction = new CompartmentDragMouseAction(dragStartElement, this, compartmentBounds);  
     dragStartElement = null;  
    }  
   }  
  }  
  
  /// <summary>  
  /// User has released the mouse button.   
  /// </summary>  
  /// <param name="sender"></param>  
  /// <param name="e"></param>  
  void compartment_MouseUp(object sender, DiagramMouseEventArgs e)  
  {  
    dragStartElement = null;  
  }  
  
  /// <summary>  
  /// Forget the source item if mouse up occurs outside the  
  /// compartment.  
  /// </summary>  
  /// <param name="e"></param>  
  public override void OnMouseUp(DiagramMouseEventArgs e)  
  {  
   base.OnMouseUp(e);  
   dragStartElement = null;  
  }  
  
  /// <summary>  
  /// Called by the Action when the user releases the mouse.  
  /// If we are still on the same compartment but in a different list item,  
  /// move the starting item to the position of the current one.  
  /// </summary>  
  /// <param name="dragFrom"></param>  
  /// <param name="e"></param>  
  public void DoMouseUp(ModelElement dragFrom, DiagramMouseEventArgs e)  
  {  
   // Original or "from" item:  
   ClassModelElement dragFromElement = dragFrom as ClassModelElement;  
   // Current or "to" item:  
   ClassModelElement dragToElement = e.HitDiagramItem.RepresentedElements.OfType<ClassModelElement>().FirstOrDefault();  
   if (dragFromElement != null && dragToElement != null)  
   {  
    // Find the common parent model element, and the relationship links:  
    ElementLink parentToLink = GetEmbeddingLink(dragToElement);  
    ElementLink parentFromLink = GetEmbeddingLink(dragFromElement);  
    if (parentToLink != parentFromLink && parentFromLink != null && parentToLink != null)  
    {  
     // Get the static relationship and role (= end of relationship):  
     DomainRelationshipInfo relationshipFrom = parentFromLink.GetDomainRelationship();  
     DomainRoleInfo parentFromRole = relationshipFrom.DomainRoles[0];  
     // Get the node in which the element is embedded, usually the element displayed in the shape:  
     ModelElement parentFrom = parentFromLink.LinkedElements[0];  
  
     // Same again for the target:  
     DomainRelationshipInfo relationshipTo = parentToLink.GetDomainRelationship();  
     DomainRoleInfo parentToRole = relationshipTo.DomainRoles[0];  
     ModelElement parentTo = parentToLink.LinkedElements[0];  
  
     // Mouse went down and up in same parent and same compartment:  
     if (parentTo == parentFrom && relationshipTo == relationshipFrom)  
     {  
      // Find index of target position:  
      int newIndex = 0;  
      var elementLinks = parentToRole.GetElementLinks(parentTo);  
      foreach (ElementLink link in elementLinks)  
      {  
       if (link == parentToLink) { break; }  
       newIndex++;  
      }  
  
      if (newIndex < elementLinks.Count)  
      {  
       using (Transaction t = parentFrom.Store.TransactionManager.BeginTransaction("Move list item"))  
       {  
        parentFromLink.MoveToIndex(parentFromRole, newIndex);  
        t.Commit();  
       }  
      }  
     }  
    }  
   }  
  }  
  
  /// <summary>  
  /// Get the embedding link to this element.  
  /// Assumes there is no inheritance between embedding relationships.  
  /// (If there is, you need to make sure you've got the relationship  
  /// that is represented in the shape compartment.)  
  /// </summary>  
  /// <param name="child"></param>  
  /// <returns></returns>  
  ElementLink GetEmbeddingLink(ClassModelElement child)  
  {  
   foreach (DomainRoleInfo role in child.GetDomainClass().AllEmbeddedByDomainRoles)  
   {  
    foreach (ElementLink link in role.OppositeDomainRole.GetElementLinks(child))  
    {  
     // Just the assume the first embedding link is the only one.  
     // Not a valid assumption if one relationship is derived from another.  
     return link;  
    }  
   }  
   return null;  
  }  
 }  
}  
  
```  
  
## <a name="see-also"></a>참고 항목  
 [응답 하 고 변경 내용 전파](../modeling/responding-to-and-propagating-changes.md)   
 [데코레이터의 속성](../modeling/properties-of-decorators.md)