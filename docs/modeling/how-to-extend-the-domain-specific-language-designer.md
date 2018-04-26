---
title: '방법: 도메인별 언어 디자이너 확장'
ms.date: 11/04/2016
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: fc41a768b54ba3253b7dad6648b77aa8c03b0f49
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-extend-the-domain-specific-language-designer"></a>방법: 도메인별 언어 디자이너 확장
사용 하 여 DSL 정의 편집 하는 디자이너 확장을 만들 수 있습니다. 형식의 확장명과 적용할 수 있는 메뉴 명령을 추가 끌어서 제스처 및 특정 유형의 값 또는 관계를 변경할 때 트리거되는 규칙을 두 번 클릭에 대 한 처리기를 추가 합니다. 확장으로는 VSIX Visual Studio Integration Extension ()를 패키지 하 고 다른 사용자에 게 배포할 수 있습니다.

 샘플 코드와이 기능에 대 한 자세한 내용은 참조는 Visual Studio [시각화 및 모델링 SDK (VMSDK) 웹 사이트](http://go.microsoft.com/fwlink/?LinkID=186128)합니다.

## <a name="setting-up-the-solution"></a>솔루션 설정
 확장 프로그램의 코드를 포함 하는 프로젝트 및 프로젝트에는 VSIX 프로젝트를 설정 합니다. 솔루션에 동일한 VSIX에 통합 하는 다른 프로젝트를 포함할 수 있습니다.

#### <a name="to-create-a-dsl-designer-extension-solution"></a>DSL 디자이너 확장 솔루션을 만들려면

1.  클래스 라이브러리 프로젝트 템플릿을 사용 하 여 새 프로젝트를 만듭니다. 에 **새 프로젝트** 대화 상자를 클릭 **Visual C#** 한 다음 가운데 창에서 클릭 **클래스 라이브러리**합니다.

     이 프로젝트에는 확장 프로그램의 코드가 포함 됩니다.

2.  VSIX 프로젝트 템플릿을 사용 하 여 새 프로젝트를 만듭니다. 에 **새 프로젝트** 대화 상자에서 **Visual C#**, 클릭 **확장성**, 한 다음 가운데 창 선택 **VSIX 프로젝트**합니다.

     선택 **솔루션에 추가**합니다.

     Source.extension.vsixmanifest은 VSIX 매니페스트 편집기에서 열립니다.

3.  콘텐츠 필드 위에 클릭 **콘텐츠 추가**합니다.

4.  에 **콘텐츠 추가** 대화 상자, 설정 **콘텐츠 형식 선택** 를 **MEF 구성 요소**, 설정 **프로젝트** 클래스 라이브러리 프로젝트에 있습니다.

5.  클릭 **버전 선택** 있는지 확인 하 고 **Visual Studio Enterprise** 을 선택 합니다.

6.  VSIX 프로젝트는 솔루션의 시작 프로젝트 인지 확인 합니다.

7.  클래스 라이브러리 프로젝트에서 다음 어셈블리에 대 한 참조를 추가 합니다.

     Microsoft.VisualStudio.CoreUtility

     Microsoft.VisualStudio.Modeling.Sdk.11.0

     Microsoft.VisualStudio.Modeling.Sdk.Diagrams.11.0

     Microsoft.VisualStudio.Modeling.Sdk.DslDefinition.11.0

     Microsoft.VisualStudio.Modeling.Sdk.Integration.11.0

     System.ComponentModel.Composition

     System.Drawing

     System.Drawing.Design

     System.Windows.Forms

## <a name="testing-and-deployment"></a>테스트 및 배포
 확장명을이 항목의 테스트를 빌드하고 솔루션을 실행 합니다. [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 의 실험적 인스턴스가 열립니다. 이 인스턴스에서 DSL 솔루션을 엽니다. DslDefinition 다이어그램을 편집 합니다. 확장 프로그램의 동작을 볼 수 있습니다.

 확장을 배포 하 고 있는 기본 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], 다른 컴퓨터에 다음이 단계를 수행 합니다.

1.  Bin의 VSIX 프로젝트에 VSIX 설치 파일을 찾거나\\*\*\\\*.vsix

2.  대상 컴퓨터에이 파일을 복사한 다음 Windows 탐색기 (또는 파일 탐색기)에서 두 번 클릭 합니다.

     [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 확장이 설치 되어 있는지 확인 하려면 확장 관리자가 열립니다.

 확장을 제거 하려면 다음이 단계를 따르십시오.

1.  [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]의 **도구** 메뉴를 클릭 하 여 **확장 관리자**합니다.

2.  확장을 선택 하 여 삭제 합니다.

## <a name="adding-a-shortcut-menu-command"></a>바로 가기 메뉴 명령을 추가
 DSL 디자이너 화면에 나타나거나 DSL 탐색기 창에서 바로 가기 메뉴 명령을 확인 하려면 다음과 같은 클래스를 작성 합니다.

 클래스를 구현 해야 `ICommandExtension` 특성이 있어야 하 고 `DslDefinitionModelCommandExtension`합니다.

```
using System.Collections.Generic;
using System.ComponentModel.Composition;
using System.Linq;
using Microsoft.VisualStudio.Modeling.Diagrams;
using Microsoft.VisualStudio.Modeling.Diagrams.ExtensionEnablement;
using Microsoft.VisualStudio.Modeling.DslDefinition;
using Microsoft.VisualStudio.Modeling.DslDefinition.ExtensionEnablement;
using Microsoft.VisualStudio.Modeling.DslDesigner;
using Microsoft.VisualStudio.Modeling.ExtensionEnablement;

namespace Fabrikam.SimpleDslDesignerExtension
{
  /// <summary>
  /// Command extending the DslDesigner.
  /// </summary>
  [DslDefinitionModelCommandExtension]
  public class MyDslDesignerCommand : ICommandExtension
  {
    /// <summary>
    /// Selection Context for this command
    /// </summary>
    [Import]
    IVsSelectionContext SelectionContext { get; set; }

    /// <summary>
    /// Is the command visible and active?
    /// This is called when the user right-clicks.
    /// </summary>
    public void QueryStatus(IMenuCommand command)
    {
      command.Visible = true;
      // Is there any selected DomainClasses in the Dsl explorer?
      command.Enabled =
        SelectionContext.AtLeastOneSelected<DomainClass>();

      // Is there any selected ClassShape on the design surface?
      command.Enabled |=
        (SelectionContext.GetCurrentSelection<ClassShape>()
                .Count() > 0);
    }
    /// <summary>
    /// Executes the command
    /// </summary>
    /// <param name="command">Command initiating this action</param>
    public void Execute(IMenuCommand command)
    {
      ...
    }
    /// <summary>
    /// Label for the command
    /// </summary>
    public string Text
    {
      get { return "My Command"; }
    }
  }
}
```

## <a name="handling-mouse-gestures"></a>마우스 제스처를 처리합니다.
 코드에 메뉴 명령의 코드와 비슷합니다.

```
[DslDefinitionModelGestureExtension]
 class MouseGesturesExtensions : IGestureExtension
 {
  /// <summary>
  /// Double-clicking on a shape representing a Domain model element displays this model element in a dialog box
  /// </summary>
  /// <param name="targetElement">Shape element on which the user has clicked</param>
  /// <param name="diagramPointEventArgs">event args for this double-click</param>
  public void OnDoubleClick(ShapeElement targetElement,
       DiagramPointEventArgs diagramPointEventArgs)
  {
   ModelElement modelElement = PresentationElementHelper.
        GetDslDefinitionModelElement(targetElement);
   if (modelElement != null)
   {
    MessageBox.Show(string.Format(
      "Double clicked on {0}", modelElement.ToString()),
      "Model element double-clicked");
   }
  }

  /// <summary>
  /// Tells if the DslDesigner can consume the to-be-dropped information
  /// </summary>
  /// <param name="targetMergeElement">Shape on which we try to drop</param>
  /// <param name="diagramDragEventArgs">Drop event</param>
  /// <returns><c>true</c> if we can consume the to be dropped data, and <c>false</c> otherwise</returns>
  public bool CanDragDrop(ShapeElement targetMergeElement,
        DiagramDragEventArgs diagramDragEventArgs)
  {
   if (diagramDragEventArgs.Data.GetDataPresent(DataFormats.FileDrop))
   {
    diagramDragEventArgs.Effect = DragDropEffects.Copy;
    return true;
   }
   return false;
  }

  /// <summary>
  /// Processes the drop by displaying the dropped text
  /// </summary>
  /// <param name="targetMergeElement">Shape on which we dropped</param>
  /// <param name="diagramDragEventArgs">Drop event</param>
  public void OnDragDrop(ShapeElement targetDropElement, DiagramDragEventArgs diagramDragEventArgs)
  {
   if (diagramDragEventArgs.Data.GetDataPresent(DataFormats.FileDrop))
   {
    string[] droppedFiles =
      diagramDragEventArgs.Data.
               GetData(DataFormats.FileDrop) as string[];
    MessageBox.Show(string.Format("Dropped text {0}",
        string.Join("\r\n", droppedFiles)), "Dropped Text");
   }
  }
 }
```

## <a name="responding-to-value-changes"></a>값이 변경에 응답
 이 처리기는 제대로 작동 하려면 도메인 모델에 필요 합니다. 간단한 도메인 모델을 제공합니다.

```
using System.Diagnostics;
using Microsoft.VisualStudio.Modeling;
using Microsoft.VisualStudio.Modeling.DslDefinition;
namespace Fabrikam.SimpleDslDesignerExtension
{
  /// <summary>
  /// Rule firing when the type of a domain model property is changed. The change is displayed
  /// in the debugger (Output window of the Visual Studio instance debugging this extension)
  /// </summary>
  [RuleOn(typeof(PropertyHasType))]
  public class DomainPropertyTypeChangedRule : RolePlayerChangeRule
  {
    /// <summary>
    /// Method called when the Type of a Domain Property
    /// is changed by the user in a DslDefinition
    /// </summary>
    /// <param name="e"></param>
    public override void RolePlayerChanged(RolePlayerChangedEventArgs e)
    {
      // We are only interested in the type
      if (e.DomainRole.Id == PropertyHasType.TypeDomainRoleId)
      {
        PropertyHasType relationship =
           e.ElementLink as PropertyHasType;
        DomainType newType = e.NewRolePlayer as DomainType;
        DomainType oldType = e.OldRolePlayer as DomainType;
        DomainProperty property = relationship.Property;

         // We write about the Type change in the debugguer
        Debug.WriteLine(string.Format("The type of the Domain property '{0}' of domain class '{1}' changed from '{2}' to '{3}'",
          property.Name,
          property.Class.Name,
          oldType.GetFullName(false),
          newType.GetFullName(false))
} }  }  );
```

 다음 코드는 간단한 모델을 구현합니다. 자리 표시자를 바꾸려면 새 GUID를 만듭니다.

```
using System;
using System.ComponentModel.Composition;
using Microsoft.VisualStudio.Modeling;
using Microsoft.VisualStudio.Modeling.DslDefinition;
namespace Fabrikam.SimpleDslDesignerExtension
{
    /// <summary>
    /// Simplest possible domain model
    /// needed only for extension rules.
    /// </summary>
    [DomainObjectId(SimpleDomainModelExtension.DomainModelId)]
    public class SimpleDomainModelExtension : DomainModel
    {
        // Id of this domain model extension
        // Please replace this with a new GUID:
        public const string DomainModelId =
                  "00000000-0000-0000-0000-000000000000";

        /// <summary>
        /// Constructor for the domain model extension
        /// </summary>
        /// <param name="store">Store in which the domain model will be loaded</param>
        public SimpleDomainModelExtension(Store store)
            : base(store, new Guid(SimpleDomainModelExtension.DomainModelId))
        {

        }

        /// <summary>
        /// Rules brought by this domain model extension
        /// </summary>
        /// <returns></returns>
        protected override System.Type[] GetCustomDomainModelTypes()
        {
            return new Type[] {
                     typeof(DomainPropertyTypeChangedRule)
                              };
        }
    }

    /// <summary>
    /// Provider for the DomainModelExtension
    /// </summary>
    [Export(typeof(DomainModelExtensionProvider))]    [ProvidesExtensionToDomainModel(typeof(DslDefinitionModelDomainModel))]
    public class SimpleDomainModelExtensionProvider
          : DomainModelExtensionProvider
    {
        /// <summary>
        /// Extension model type
        /// </summary>
        public override Type DomainModelType
        {
            get
            {
                return typeof(SimpleDomainModelExtension);
            }
        }

    }
}
```