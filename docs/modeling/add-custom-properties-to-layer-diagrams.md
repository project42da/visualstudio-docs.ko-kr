---
title: "종속성 다이어그램을 사용자 지정 속성을 추가 합니다. | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- dependency diagrams, adding custom properties
ms.assetid: 52b3ac25-d10b-4507-a1fe-209ccb4d2777
caps.latest.revision: 21
author: alexhomer1
ms.author: ahomer
manager: douge
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 8f84f22444a5df5b9f4f4af44cd8ee9136403467
ms.openlocfilehash: 6c7e43c180ac5210d9c29961ed7330b370a99075
ms.lasthandoff: 02/22/2017

---
# <a name="add-custom-properties-to-dependency-diagrams"></a>종속성 다이어그램에 사용자 지정 속성 추가
종속성 다이어그램에 대 한 확장 코드를 작성할 때 종속성 다이어그램에서 모든 요소를 사용 하 여 값을 저장할 수 있습니다. 값은 다이어그램이 저장되고 다시 열릴 때 유지됩니다. 이러한 속성에 나타날 수도 있습니다는 **속성** 창 사용자가 보고 편집할 수 있도록 합니다. 예를 들어 사용자가 각 레이어에 대한 정규식을 지정하고, 각 레이어의 클래스 이름이 사용자가 지정한 패턴을 따르는지 확인하기 위해 유효성 검사 코드를 작성하도록 허용할 수 있습니다.  
  
## <a name="properties-not-visible-to-the-user"></a>사용자에게 표시되지 않는 속성  
 종속성 다이어그램의 요소에 값을 연결 하는 코드를 하려는 경우 MEF 구성 요소를 정의할 필요가 없습니다. 명명 된는 사전이 `Properties` <xref:Microsoft.VisualStudio.ArchitectureTools.Extensibility.Layer.ILayerElement>.</xref:Microsoft.VisualStudio.ArchitectureTools.Extensibility.Layer.ILayerElement> 레이어 요소의 사전에 마샬링할 수 값을 추가하기만 하면 됩니다. 종속성 다이어그램의 일부로 저장 됩니다. 자세한 내용은 참조 [탐색 및 업데이트 프로그램 코드에서 모델 계층](../modeling/navigate-and-update-layer-models-in-program-code.md)합니다.  
  
## <a name="properties-that-the-user-can-edit"></a>사용자가 편집할 수 있는 속성  
 **초기 준비**  
  
> [!IMPORTANT]
>  속성을 표시하려면 레이어 속성을 표시할 각 컴퓨터에서 다음과 같이 변경해야 합니다.  
>   
>  1.  메모장을 사용 하 여 실행 **관리자 권한으로 실행**합니다. 
          `%ProgramFiles%\Microsoft Visual Studio [version]\Common7\IDE\Extensions\Microsoft\Architecture Tools\ExtensibilityRuntime\extension.vsixmanifest`를 엽니다.  
> 2.  
          `Content` 요소 안에 다음을 추가합니다.  
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
  
 속성이 명령, 제스처 또는 유효성 검사 프로젝트의 일부인 경우 아무 것도 추가할 필요가 없습니다. 사용자 지정 속성에 대한 코드는 MEF 구성 요소로 정의된 Visual Studio 확장성 프로젝트에 정의되어야 합니다. 자세한 내용은 참조 [종속성 다이어그램에 명령 및 제스처 추가](../modeling/add-commands-and-gestures-to-layer-diagrams.md) 또는 [종속성 다이어그램에 사용자 지정 아키텍처 유효성 검사 추가](../modeling/add-custom-architecture-validation-to-layer-diagrams.md)합니다.  
  
 **사용자 지정 속성을 정의 합니다.**  
  
 사용자 지정 속성을 만들려면 다음과 같이 클래스를 정의합니다.  
  
```  
[Export(typeof(IPropertyExtension))]  
public class MyProperty   
      : PropertyExtension<ILayerElement>  
{  
  // Implement the interface.  
}  
```  
  
 속성을 정의할 수 있습니다 <xref:Microsoft.VisualStudio.ArchitectureTools.Extensibility.Layer.ILayerElement>또는 해당 파생된 클래스를 포함 하는 중:</xref:Microsoft.VisualStudio.ArchitectureTools.Extensibility.Layer.ILayerElement>  
  
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
 [종속성 다이어그램을 확장 합니다.](../modeling/extend-layer-diagrams.md)

