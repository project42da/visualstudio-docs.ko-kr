---
title: 종속성 다이어그램에 사용자 지정 속성 추가 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- dependency diagrams, adding custom properties
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: fbdf0587b6bba938ddc178842939c14c9079a2a0
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="add-custom-properties-to-dependency-diagrams"></a>종속성 다이어그램에 사용자 지정 속성 추가
종속성 다이어그램에 대 한 확장 프로그램 코드를 작성할 때 종속성 다이어그램에서 모든 요소를 사용 하 여 값을 저장할 수 있습니다. 값은 다이어그램이 저장되고 다시 열릴 때 유지됩니다. 이러한 속성에 나타날 수 있습니다는 **속성** 창이 보고 편집할 수 있도록 합니다. 예를 들어 사용자가 각 레이어에 대한 정규식을 지정하고, 각 레이어의 클래스 이름이 사용자가 지정한 패턴을 따르는지 확인하기 위해 유효성 검사 코드를 작성하도록 허용할 수 있습니다.  
  
## <a name="properties-not-visible-to-the-user"></a>사용자에게 표시되지 않는 속성  
 종속성 다이어그램의 모든 요소에 값을 연결 하는 프로그램 코드를 원하는 경우 MEF 구성 요소를 정의할 필요가 없습니다. `Properties`에는 <xref:Microsoft.VisualStudio.ArchitectureTools.Extensibility.Layer.ILayerElement>라는 사전이 있습니다. 레이어 요소의 사전에 마샬링할 수 값을 추가하기만 하면 됩니다. 종속성 다이어그램의 일부로 저장 됩니다. 자세한 내용은 참조 [탐색 및 업데이트 프로그램 코드에서 모델을 계층](../modeling/navigate-and-update-layer-models-in-program-code.md)합니다.  
  
## <a name="properties-that-the-user-can-edit"></a>사용자가 편집할 수 있는 속성  
 **초기 준비**  
  
> [!IMPORTANT]
>  속성을 표시하려면 레이어 속성을 표시할 각 컴퓨터에서 다음과 같이 변경해야 합니다.  
>   
>  1.  메모장을 사용 하 여 실행 **관리자 권한으로 실행**합니다. `%ProgramFiles%\Microsoft Visual Studio [version]\Common7\IDE\Extensions\Microsoft\Architecture Tools\ExtensibilityRuntime\extension.vsixmanifest`를 엽니다.  
> 2.  `Content` 요소 안에 다음을 추가합니다.  
>   
>     ```xml  
>     <MefComponent>Microsoft.VisualStudio.ArchitectureTools.Extensibility.Layer.Provider.dll</MefComponent>  
>     ```  
> 3.  아래는 **Visual Studio Tools** Visual Studio 응용 프로그램 시작 메뉴를 열고 섹션 **개발자 명령 프롬프트**합니다.  
>   
>      다음을 입력합니다.  
>   
>      `devenv /rootSuffix /updateConfiguration`  
>   
>      `devenv /rootSuffix Exp /updateConfiguration`  
> 4.  Visual Studio를 다시 시작합니다.  
  
 **코드가 VSIX 프로젝트에 있는지 확인**  
  
 속성이 명령, 제스처 또는 유효성 검사 프로젝트의 일부 이면 아무 것도 추가할 필요가 없습니다. 사용자 지정 속성에 대한 코드는 MEF 구성 요소로 정의된 Visual Studio 확장성 프로젝트에 정의되어야 합니다. 자세한 내용은 참조 [종속성 다이어그램에 명령 및 제스처 추가](../modeling/add-commands-and-gestures-to-layer-diagrams.md) 또는 [종속성 다이어그램에 사용자 지정 아키텍처 유효성 검사를 추가](../modeling/add-custom-architecture-validation-to-layer-diagrams.md)합니다.  
  
 **사용자 지정 속성 정의**  
  
 사용자 지정 속성을 만들려면 다음과 같이 클래스를 정의합니다.  
  
```  
[Export(typeof(IPropertyExtension))]  
public class MyProperty   
      : PropertyExtension<ILayerElement>  
{  
  // Implement the interface.  
}  
```  
  
 <xref:Microsoft.VisualStudio.ArchitectureTools.Extensibility.Layer.ILayerElement> 또는 해당 파생 클래스에서 다음과 같은 속성을 정의할 수 있습니다.  
  
-   `ILayerModel` - 모델  
  
-   `ILayer` - 각 레이어  
  
-   `ILayerDependencyLink` - 레이어 간의 링크  
  
-   `ILayerComment`  
  
-   `ILayerCommentLink`  
  
## <a name="example"></a>예제  
 다음 코드는 일반적인 사용자 지정 속성 설명자입니다. 레이어 모델(`ILayerModel`)에서 사용자가 사용자 지정 유효성 검사 메서드의 값을 제공할 수 있게 해주는 부울 속성을 정의합니다.  
  
```  
using System;  
using System.ComponentModel.Composition;  
using Microsoft.VisualStudio.ArchitectureTools.Extensibility.Layer;  
  
namespace MyNamespace  
{  
  /// <summary>  
  /// Custom properties are added to the Layer Designer via a custom  
  /// Property Descriptor. We have to export this Property Descriptor  
  /// using MEF to make it available in the Layer Designer.  
  /// </summary>  
  [Export(typeof(IPropertyExtension))]  
  public class AllTypesMustBeReferencedProperty   
      : PropertyExtension<ILayerModel>  
  {  
    /// <summary>  
    /// Each custom property must have a unique name.   
    /// Usually we use the full name of this class.  
    /// </summary>  
    public static readonly string FullName =  
      typeof(AllTypesMustBeReferencedProperty).FullName;  
  
    /// <summary>  
    /// Construct the property. Notice the use of FullName.  
    /// </summary>  
    public AllTypesMustBeReferencedProperty()  
            : base(FullName)  
    {  }  
  
    /// <summary>  
    /// The display name is shown in the Properties window.  
    /// We therefore use a localizable resource.  
    /// </summary>  
    public override string DisplayName  
    {  
      get { return Strings.AllTypesMustBeReferencedDisplayName; }  
    }  
  
    /// <summary>  
    /// Description shown at the bottom of the Properties window.  
    /// We use a resource string for easier localization.  
    /// </summary>  
    public override string Description  
    {  
      get { return Strings.AllTypesMustBeReferencedDescription; }  
    }  
  
    /// <summary>  
    /// This is called to set a new value for this property. We must  
    /// throw an exception if the value is invalid.  
    /// </summary>  
    /// <param name="component">The target ILayerElement</param>  
    /// <param name="value">The new value</param>  
    public override void SetValue(object component, object value)  
    {  
      ValidateValue(value);  
      base.SetValue(component, value);  
    }  
    /// <summary>  
    /// Helper to validate the value.  
    /// </summary>  
    /// <param name="value">The value to validate</param>  
    private static void ValidateValue(object value)  
    {  }  
  
    public override Type PropertyType  
    { get { return typeof(bool); } }  
  
    /// <summary>  
    /// The segment label of the properties window.  
    /// </summary>  
    public override string Category  
    {   
      get  
      {  
        return Strings.AllTypesMustBeReferencedCategory;  
      }  
    }  
  }  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [종속성 다이어그램 확장](../modeling/extend-layer-diagrams.md)
