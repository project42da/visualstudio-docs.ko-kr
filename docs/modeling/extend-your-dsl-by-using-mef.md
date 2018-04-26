---
title: MEF를 사용하여 DSL 확장
ms.date: 11/04/2016
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: 8cc48c70cd6fe8bd45ed65b96732d3db31a386e2
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="extend-your-dsl-by-using-mef"></a>MEF를 사용하여 DSL 확장
프레임 워크 MEF (Managed Extensibility)를 사용 하 여 해당 도메인 특정 언어 DSL ()를 확장할 수 있습니다. 또는 다른 개발자 DSL 정 및 프로그램 코드를 변경 하지 않고 DSL에 대 한 확장을 작성 하는 일을 할 수 있습니다. 이러한 확장 메뉴 명령, 끌어서 놓기 처리기 및 유효성 검사를 포함 합니다. 사용자는 DSL을 설치 하 고 다음에 대 한 필요에 따라 확장을 설치 하는 작업을 할 수 있습니다.

 또한 DSL에서 MEF를 사용 하도록 설정 하면 수 쉽게 DSL의 기능 중 일부를 쓸 수는 모든 DSL 함께 빌드된 경우에 합니다.

 MEF에 대 한 자세한 내용은 참조 [Framework MEF (Managed Extensibility)](/dotnet/framework/mef/index)합니다.

### <a name="to-enable-your-dsl-to-be-extended-by-mef"></a>MEF에서 확장 되어야 DSL을 사용 하도록 설정 하려면

1.  라는 새 폴더 만들기 **MefExtension** 내는 **DslPackage** 프로젝트. 다음 파일을 추가 합니다.

     파일 이름: `CommandExtensionVSCT.tt`

    > [!IMPORTANT]
    >  GUID DslPackage\GeneratedCode\Constants.tt에 정의 된 GUID CommandSetId와 동일 하 게이 파일에 설정

    ```
    <#@ Dsl processor="DslDirectiveProcessor" requires="fileName='..\..\Dsl\DslDefinition.dsl'" #>
    <#
    // CmdSet Guid must be defined before master template is included
    // This Guid must be kept synchronized with the CommandSetId Guid in Constants.tt
    Guid guidCmdSet = new Guid ("00000000-0000-0000-0000-000000000000");
    string menuidCommandsExtensionBaseId="0x4000";
    #>
    <#@ include file="DslPackage\CommandExtensionVSCT.tt" #>
    ```

     파일 이름: `CommandExtensionRegistrar.tt`

    ```
    <#@ Dsl processor="DslDirectiveProcessor" requires="fileName='..\..\Dsl\DslDefinition.dsl'" #>
    <#@ include file="DslPackage\CommandExtensionRegistrar.tt" #>
    ```

     파일 이름: `ValidationExtensionEnablement.tt`

    ```
    <#@ Dsl processor="DslDirectiveProcessor" requires="fileName='..\..\Dsl\DslDefinition.dsl'" #>
    <#@ include file="DslPackage\ValidationExtensionEnablement.tt" #>
    ```

     파일 이름: `ValidationExtensionRegistrar.tt`

     이 파일을 추가 하는 경우에서 설정 해야 유효성 검사 DSL의 스위치 중 하나 이상을 사용 하 여 **EditorValidation** DSL 탐색기에서.

    ```
    <#@ Dsl processor="DslDirectiveProcessor" requires="fileName='..\..\Dsl\DslDefinition.dsl'" #>
    <#@ include file="DslPackage\ValidationExtensionRegistrar.tt" #>
    ```

     파일 이름: `PackageExtensionEnablement.tt`

    ```
    <#@ Dsl processor="DslDirectiveProcessor" requires="fileName='..\..\Dsl\DslDefinition.dsl'" #>
    <#@ include file="DslPackage\PackageExtensionEnablement.tt" #>
    ```

2.  라는 새 폴더 만들기 **MefExtension** 내는 **Dsl** 프로젝트. 다음 파일을 추가 합니다.

     파일 이름: `DesignerExtensionMetaDataAttribute.tt`

    ```
    <#@ Dsl processor="DslDirectiveProcessor" requires="fileName='..\..\Dsl\DslDefinition.dsl'" #>
    <#@ include file="Dsl\DesignerExtensionMetadataAttribute.tt" #>
    ```

     파일 이름: `GestureExtensionEnablement.tt`

    ```
    <#@ Dsl processor="DslDirectiveProcessor" requires="fileName='..\..\Dsl\DslDefinition.dsl'" #>
    <#@ include file="Dsl\GestureExtensionEnablement.tt" #>
    ```

     파일 이름: `GestureExtensionController.tt`

    ```
    <#@ Dsl processor="DslDirectiveProcessor" requires="fileName='..\..\Dsl\DslDefinition.dsl'" #>
    <#@ include file="Dsl\GestureExtensionController.tt" #>
    ```

3.  명명 된 기존 파일에 다음 줄 추가 **DslPackage\Commands.vsct**:

    ```
    <Include href="MefExtension\CommandExtensionVSCT.vsct"/>
    ```

     기존 줄 삽입 `<Include>` 지시문입니다.

4.  `Open DslDefinition.dsl.`

5.  DSL 탐색기에서 선택 **Editor\Validation**합니다.

6.  속성 창에서 명명 된 속성 중 하나 이상 있는지 확인 **사용...**  은 `true`합니다.

7.  솔루션 탐색기 도구 모음에서 클릭 **모든 템플릿 변형**합니다.

     보조 파일의 각 사용자가 추가한 파일 아래에 나타납니다.

8.  빌드하고 여전히 작동 하는지 확인 하도록 솔루션을 실행 합니다.

 DSL은 이제 MEF 설정 있습니다. MEF 확장으로 메뉴 명령, 제스처 처리기 및 유효성 검사 제약 조건을 작성할 수 있습니다. 다른 사용자 지정 코드와 함께 DSL 솔루션에서 이러한 확장을 작성할 수 있습니다. 또한, 또는 다른 개발자가 작성할 수 별도 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] DSL를 확장 하는 확장 합니다.

## <a name="creating-an-extension-for-a-mef-enabled-dsl"></a>MEF를 사용 하는 DSL에 대 한 확장 만들기
 사용자가 직접 또는 다른 사용자가 만든 MEF 사용이 가능한 DSL에는 액세스할 수 있으면 그에 대 한 확장을 작성할 수 있습니다. 확장 메뉴 명령, 제스처 처리기 또는 유효성 검사 제약 조건을 추가 하려면 사용할 수 있습니다. 사용 하면 이러한 확장을 작성 하는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 확장 (VSIX) 솔루션입니다. 솔루션에는 두 부분이: 코드 어셈블리를 작성 하는 클래스 라이브러리 프로젝트 및 어셈블리를 패키지 하는 VSIX 프로젝트.

#### <a name="to-create-a-dsl-extension-vsix"></a>DSL VSIX 확장을 만들려면

1.  새 클래스 라이브러리 프로젝트를 만듭니다. 이 수행 하는 **새 프로젝트** 대화 상자에서 **Visual Basic** 또는 **Visual C#** 선택한 후 **클래스 라이브러리**합니다.

2.  새 클래스 라이브러리 프로젝트에서 DSL의 어셈블리에 대 한 참조를 추가 합니다.

    -   이 어셈블리는 일반적으로로 끝나는 이름에 "입니다. Dsl.dll "입니다.

    -   DSL 프로젝트에 액세스할 수 있는 경우에 디렉터리 아래에 있는 어셈블리 파일을 찾을 수 있습니다 **Dsl\bin\\\***

    -   DSL VSIX 파일에 액세스할 수 있으면 ".zip" VSIX 파일의 파일 이름 확장명을 변경 하 여 어셈블리를 찾을 수 있습니다. .Zip 파일을 압축을 풉니다.

3.  다음.NET 어셈블리에 대 한 참조를 추가 합니다.

    -   Microsoft.VisualStudio.Modeling.Sdk.11.0.dll

    -   Microsoft.VisualStudio.Modeling.Sdk.Diagrams.11.0.dll

    -   Microsoft.VisualStudio.Modeling.Sdk.Shell.11.0.dll

    -   System.ComponentModel.Composition.dll

    -   System.Windows.Forms.dll

4.  동일한 솔루션에서 VSIX 프로젝트를 만듭니다. 이 수행 하는 **새 프로젝트** 대화 상자에서 **Visual Basic** 또는 **Visual C#**, 클릭 **확장성**를 선택한 후  **VSIX 프로젝트**합니다.

5.  솔루션 탐색기에서 VSIX 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 클릭 **시작 프로젝트로 설정**합니다.

6.  새 프로젝트를 열고 **source.extension.vsixmanifest**합니다.

7.  클릭 **콘텐츠 추가**합니다. 대화 상자에서 설정 **콘텐츠 형식** 를 **MEF 구성 요소**, 및 **소스 프로젝트** 클래스 라이브러리 프로젝트에 있습니다.

8.  DSL에 대 한 VSIX 참조를 추가 합니다.

    1.  **source.extension.vsixmanifest**, 클릭 **참조 추가**

    2.  대화 상자에서 클릭 **추가 페이로드** 를 DSL의 VSIX 파일을 찾습니다. VSIX 파일에에서 기본 제공 되 DSL 솔루션에 **DslPackage\bin\\\*** 합니다.

         이렇게 하면 동시에 DSL 및 확장 프로그램을 설치 하는 사용자가 있습니다. 사용자가 이미 DSL을 설치 하 고, 확장만 설치 됩니다.

9. 검토 및 업데이트의 다른 필드 **source.extension.vsixmanifest**합니다. 클릭 **버전 선택** 되어 있는지 확인 하 고 올바른 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 버전 설정 됩니다.

10. 클래스 라이브러리 프로젝트에 코드를 추가 합니다. 다음 섹션에는 예제를 사용 하 여를 참조 합니다.

     원하는 수의 명령, 제스처 및 유효성 검사 클래스를 추가할 수 있습니다.

11. 확장을 테스트 하려면 **F5**합니다. 실험적 인스턴스에서 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]를 만들거나 DSL의 예제 파일을 엽니다.

## <a name="writing-mef-extensions-for-dsls"></a>Dsl에 대 한 MEF 확장을 작성
 별도 DSL 확장 솔루션의 어셈블리 코드 프로젝트에 확장을 작성할 수 있습니다. DSL의 일부로 명령, 제스처 및 유효성 검사 코드를 작성 하는 편리한 방법으로 DslPackage 프로젝트에서 MEF를 사용할 수 있습니다.

### <a name="menu-commands"></a>메뉴 명령
 메뉴 명령을 작성 하기 위해 구현 하는 클래스 정의 <xref:Microsoft.VisualStudio.Modeling.ExtensionEnablement.ICommandExtension> 라는 DSL에 정의 된 특성이 있는 클래스를 접두사 *YourDsl*`CommandExtension`합니다. 둘 이상의 메뉴 명령 클래스를 작성할 수 있습니다.

 `QueryStatus()` 다이어그램을 마우스 오른쪽 단추로 클릭할 때마다 호출 됩니다. 현재 선택 영역을 검사 하 고 설정 `command.Enabled` 를 나타내는 명령이 적용 됩니다.

```
using System.ComponentModel.Composition;
using System.Linq;
using Company.MyDsl; // My DSL
using Company.MyDsl.ExtensionEnablement; // My DSL
using Microsoft.VisualStudio.Modeling; // Transactions
using Microsoft.VisualStudio.Modeling.Diagrams.ExtensionEnablement; // IVsSelectionContext
using Microsoft.VisualStudio.Modeling.ExtensionEnablement; // ICommandExtension

namespace MyMefExtension
{
  // Defined in Dsl\MefExtension\DesignerExtensionMetaDataAttribute.cs:
  [MyDslCommandExtension]
  public class MyCommandClass : ICommandExtension
  {
    /// <summary>
    /// Provides access to current document and selection.
    /// </summary>
    [Import]
    IVsSelectionContext SelectionContext { get; set; }

    /// <summary>
    /// Called when the user selects this command.
    /// </summary>
    /// <param name="command"></param>
    public void Execute(IMenuCommand command)
    {
      // Transaction is required if you want to update elements.
      using (Transaction t = SelectionContext.CurrentStore
              .TransactionManager.BeginTransaction("fix names"))
      {
        foreach (ExampleShape shape in SelectionContext.CurrentSelection)
        {
          ExampleElement element = shape.ModelElement as ExampleElement;
          element.Name = element.Name + " !";
        }
        t.Commit();
      }
    }

    /// <summary>
    /// Called when the user right-clicks the diagram.
    /// Determines whether the command should appear.
    /// This method should set command.Enabled and command.Visible.
    /// </summary>
    /// <param name="command"></param>
    public void QueryStatus(IMenuCommand command)
    {
      command.Enabled =
        command.Visible = (SelectionContext.CurrentSelection.OfType<ExampleShape>().Count() > 0);
    }

    /// <summary>
    /// Called when the user right-clicks the diagram.
    /// Determines the text of the command in the menu.
    /// </summary>
    public string Text
    {
      get { return "My menu command"; }
    }
  }
}

```

### <a name="gesture-handlers"></a>제스처 처리기
 개체의 내부 또는 외부 어디에서 나 다이어그램으로 끌어와 제스처 처리기를 처리할 수 있는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]합니다. 다음 예제에서는 Windows 탐색기에서 파일을 다이어그램으로 끌어 놓을 수 있습니다. 파일 이름을 포함 하는 요소를 만듭니다.

 끌기 다른 DSL 모델 및 UML 모델에서 처리 하는 처리기를 작성할 수 있습니다. 자세한 내용은 참조 [하는 방법: 끌어서 놓기 처리기를 추가](../modeling/how-to-add-a-drag-and-drop-handler.md)합니다.

```

using System.ComponentModel.Composition;
using System.Linq;
using Company.MyDsl;
using Company.MyDsl.ExtensionEnablement;
using Microsoft.VisualStudio.Modeling; // Transactions
using Microsoft.VisualStudio.Modeling.Diagrams;
using Microsoft.VisualStudio.Modeling.Diagrams.ExtensionEnablement;
using Microsoft.VisualStudio.Modeling.ExtensionEnablement;

namespace MefExtension
{
  [MyDslGestureExtension]
  class MyGestureExtension : IGestureExtension
  {
    public void OnDoubleClick(ShapeElement targetElement, DiagramPointEventArgs diagramPointEventArgs)
    {
      System.Windows.Forms.MessageBox.Show("double click!");
    }

    /// <summary>
    /// Called when the user drags anything over the diagram.
    /// Return true if the dragged object can be dropped on the current target.
    /// </summary>
    /// <param name="targetMergeElement">The shape or diagram that the mouse is currently over</param>
    /// <param name="diagramDragEventArgs">Data about the dragged element.</param>
    /// <returns></returns>
    public bool CanDragDrop(ShapeElement targetMergeElement, DiagramDragEventArgs diagramDragEventArgs)
    {
      // This handler only allows items to be dropped onto the diagram:
      return targetMergeElement is MefDsl2Diagram &&
      // And only accepts files dragged from Windows Explorer:
        diagramDragEventArgs.Data.GetFormats().Contains("FileNameW");
    }

    /// <summary>
    /// Called when the user drops an item onto the diagram.
    /// </summary>
    /// <param name="targetDropElement"></param>
    /// <param name="diagramDragEventArgs"></param>
    public void OnDragDrop(ShapeElement targetDropElement, DiagramDragEventArgs diagramDragEventArgs)
    {
      MefDsl2Diagram diagram = targetDropElement as MefDsl2Diagram;
      if (diagram == null) return;

      // This handler only accepts files dragged from Windows Explorer:
      string[] draggedFileNames = diagramDragEventArgs.Data.GetData("FileNameW") as string[];
      if (draggedFileNames == null || draggedFileNames.Length == 0) return;

      using (Transaction t = diagram.Store.TransactionManager.BeginTransaction("file names"))
      {
        // Create an element to represent each file:
        foreach (string fileName in draggedFileNames)
        {
          ExampleElement element = new ExampleElement(diagram.ModelElement.Partition);
          element.Name = fileName;

          // This method of adding the new element allows the position
          // of the shape to be specified:
          ElementGroup group = new ElementGroup(element);
          diagram.ElementOperations.MergeElementGroupPrototype(
            diagram, group.CreatePrototype(), PointD.ToPointF(diagramDragEventArgs.MousePosition));
        }
        t.Commit();
      }
    }
  }
}

```

### <a name="validation-constraints"></a>유효성 검사 제약 조건
 유효성 검사 메서드는으로 표시 되는 `ValidationExtension` DSL, 고도 의해 생성 되는 특성 <xref:Microsoft.VisualStudio.Modeling.Validation.ValidationMethodAttribute>합니다. 메서드 특성에 의해 표시 되지 않은 모든 클래스에 나타날 수 있습니다.

 자세한 내용은 참조 [도메인 특정 언어의 유효성 검사](../modeling/validation-in-a-domain-specific-language.md)합니다.

```
using Company.MyDsl;
using Company.MyDsl.ExtensionEnablement;
using Microsoft.VisualStudio.Modeling.Validation;

namespace MefExtension
{
  class MyValidationExtension // Can be any class.
  {
    // SAMPLE VALIDATION METHOD.
    // All validation methods have the following attributes.

    // Specific to the extended DSL:
    [MyDslValidationExtension]

    // Determines when validation is applied:
    [ValidationMethod(
       ValidationCategories.Save
     | ValidationCategories.Open
     | ValidationCategories.Menu)]

    /// <summary>
    /// When validation is executed, this method is invoked
    /// for every element in the model that is an instance
    /// of the second parameter type.
    /// </summary>
    /// <param name="context">For reporting errors</param>
    /// <param name="elementToValidate"></param>
    private void ValidateClassNames
      (ValidationContext context,
       // Type determines to what elements this will be applied:
       ExampleElement elementToValidate)
    {
      // Write code here to test values and links.
      if (elementToValidate.Name.IndexOf(' ') >= 0)
      {
        // Log any unacceptable values:
        context.LogError(
          // Description:
          "Name must not contain spaces"
          // Error code unique to this type of error:
          , "MyDsl001"
          // Element to highlight when user double-clicks error:
          , elementToValidate);
} } } }

```

## <a name="see-also"></a>참고 항목

- [Visual Studio 확장 전달](../extensibility/shipping-visual-studio-extensions.md)
- [MEF(Managed Extensibility Framework)](/dotnet/framework/mef/index)
- [방법: 끌어서 놓기 처리기 추가](../modeling/how-to-add-a-drag-and-drop-handler.md)
- [도메인별 언어에서 유효성 검사](../modeling/validation-in-a-domain-specific-language.md)