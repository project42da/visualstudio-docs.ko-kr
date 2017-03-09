---
title: "옵션 페이지 사용 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "도구 옵션 페이지[Visual Studio SDK], 사용"
ms.assetid: 5ae6b995-3aeb-43a7-9786-4cf69faa101c
caps.latest.revision: 36
caps.handback.revision: 36
manager: "douge"
---
# 옵션 페이지 사용
[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 자동화 모델은 VSPackage가 **도구** 메뉴에서 **옵션** 대화 상자에 액세스할 수 있도록 <xref:EnvDTE.DTE> 개체를 제공합니다.  
  
 일반적으로 **옵션** 대화 상자의 페이지는 페이지가 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] IDE\(통합 개발 환경\)에서 제공되든지 아니면 VSPackage에서 제공되든지 자동화 모델을 사용하여 액세스할 수 있습니다. 그러나 다음과 같은 몇 가지 예외가 있습니다.  
  
-   **동적 도움말** 페이지의 설정은 프로그래밍 방식으로 액세스할 수 없습니다.**동적 도움말** 기능은 자동화 모델을 사용하여 제어할 수 있지만 제어는 코드로 직접 수행해야 합니다. 자세한 내용은 [How to: Control the Dynamic Help Window](http://msdn.microsoft.com/ko-kr/7f5777aa-c270-4058-a175-8ce8a4ed25eb)을 참조하세요.  
  
-   **글꼴 및 색상** 페이지 설정의 제어는 자동화 모델이 아닌 자체 API를 통해 제공됩니다. 자세한 내용은 [글꼴 및 색을 사용 하 여](../extensibility/using-fonts-and-colors.md)을 참조하세요.  
  
-   자동화 모델을 통해 언어별 속성을 가져올 수 없습니다.  
  
 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 자동화 모델을 지원하지 않는 **옵션** 페이지는 쿼리할 때 자동화 <xref:EnvDTE.Properties> 컬렉션을 반환하지 않을 수 있습니다. 컬렉션이 반환되는 경우 일부 기능이 없습니다. 이러한 기능을 관리하는 방법에 대한 자세한 내용은 [DTE Properties Collections](../Topic/DTE%20Properties%20Collections.md)을 참조하세요.  
  
## 옵션 페이지 관리  
 **옵션** 페이지를 관리하려면 VSPackage가 자동화 모델에서 <xref:EnvDTE.DTE> 개체를 가져와야 합니다.  
  
> [!NOTE]
>  VSPackage가 자동화 모델을 사용하여 설치된 **옵션** 페이지의 설정을 쿼리하고 변경할 때 IDE 기능을 확장하지 않습니다. 따라서 패키지가 자동화 개체를 구현하지 않아도 됩니다.  
  
 자동화 모델을 통해 <xref:EnvDTE.DTE> 개체를 가져오려면 다음과 같이 <xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider.QueryService%2A> 메서드를 호출하고 `SID_SDTE`의 서비스 ID 인수 및 `IID__DTE`의 인터페이스 인수를 호출합니다.  
  
```  
pServiceProvider->QueryService(SID_SDTE, IID__DTE, (LPVOID*)pDTE);  
```  
  
 MPF\(관리되는 패키지 프레임워크\)를 사용하여 <xref:EnvDTE.DTE> 개체를 가져오려면 <xref:Microsoft.VisualStudio.Shell.Package.GetService%2A> 메서드를 호출하고 <xref:Microsoft.VisualStudio.Shell.Interop.SDTE> 형식의 `serviceType` 매개 변수를 제공합니다.  
  
 [!code-cs[UI_UserSettings_ToolsOptionPages#01](../extensibility/internals/codesnippet/CSharp/using-options-pages_1.cs)]
 [!code-vb[UI_UserSettings_ToolsOptionPages#01](../extensibility/internals/codesnippet/VisualBasic/using-options-pages_1.vb)]  
  
 **옵션** 페이지는 두 개의 식별자로 지정됩니다. 첫 번째 식별자는 **옵션** 페이지가 포함된 폴더를 나타내는 문자열입니다. 두 번째 식별자는 해당 폴더의 특정 항목을 나타내는 문자열입니다. 이들은 **옵션** 페이지 범주와 하위 범주 또는 항목과 하위 항목이라고 합니다.  
  
 예를 들어 기본 코드를 처리하기 위한 텍스트 편집기 설정은 **텍스트 편집기** 폴더의 **기본** 멤버로 탐색 창에 있습니다. 범주에 대한 식별자는 `TextEditor`이고 하위 범주는 `Basic`이며 **옵션** 페이지 자체는 `TextEditor.Basic` 페이지라고 합니다.  
  
> [!NOTE]
>  지역화 및 기타 이유로 **옵션** 페이지에 표시된 이름이 범주와 하위 범주 식별자로 사용된 문자열과 다를 수 있습니다. 식별자가 다른 곳에서 문서화되지 않은 경우 IDE를 쿼리하는 데 자동화를 사용해야 올바른 식별자를 가져올 수 있습니다. 레지스트리 위치는 HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\VisualStudio\\*\<VS 버전\>*\\AutomationProperties이며, 여기서 *\<VS 버전\>*은 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]의 릴리스 버전 번호입니다. 자세한 내용은 [사용자 지정 옵션 페이지 등록](../misc/registering-custom-options-pages.md)을 참조하세요.  
  
 다음 예제를 사용하여 자동화 모델을 통해 `TextEditor.Basic` 페이지의 속성을 가져올 수 있습니다.  
  
```  
CComPtr<_DTE> srpDTE; CComPtr<Properties> srpDTEPropertiesList; hr = srpDTE->get_Properties("TextEditor", "Basic", &srpDTEPropertiesList);  
```  
  
 MPF를 사용하여 속성을 가져오려면 <xref:EnvDTE._DTE.Properties%2A> 메서드를 사용합니다.  
  
 [!code-cs[UI_UserSettings_ToolsOptionPages#02](../extensibility/internals/codesnippet/CSharp/using-options-pages_2.cs)]
 [!code-vb[UI_UserSettings_ToolsOptionPages#02](../extensibility/internals/codesnippet/VisualBasic/using-options-pages_2.vb)]  
  
 <xref:EnvDTE.Properties.Item%2A> 메서드는 <xref:EnvDTE.Properties> 컬렉션의 개별 설정을 <xref:EnvDTE.Property> 개체로 반환합니다.  
  
 범주 및 하위 범주와 마찬가지로 각 설정에 고유한 문자열인 식별자가 있습니다. 예를 들어 `TextEditor.Basic` 페이지의 **탭 크기** 설정은 문자열, `TabSize`로 식별됩니다.  
  
> [!NOTE]
>  지역화 및 기타 이유로 **옵션** 페이지에 표시되는 이름이 설정 식별자로 사용되는 문자열과 다를 수 있습니다. 식별자가 다른 곳에서 문서화되지 않은 경우 IDE를 쿼리하는 데 자동화를 사용해야 올바른 식별자를 가져올 수 있습니다.  
  
 <xref:EnvDTE.Properties> 컬렉션의 <xref:EnvDTE.Properties.Item%2A> 메서드에서 반환되는 <xref:EnvDTE.Property> 개체의 <xref:EnvDTE.Property.Value%2A>를 사용하여 설정 상태를 쿼리하고 변경할 수 있습니다.  
  
 예를 들어 자동화 모델을 통해 `TextEditor.Basic` 페이지에서 **탭 크기** 설정을 지정하려면 다음 예제에서 반환되는 <xref:EnvDTE.Properties> 개체를 사용합니다.  
  
```  
CComPtr<Property> srpProperty; hr = srpDTEPropertiesList->Item("TabSize", &srpProperty); hr= srpProperty.set_Value(4);  
```  
  
 다음 예제는 MPF를 사용하여 **탭 크기** 설정을 업데이트하는 방법을 보여 줍니다.  
  
 [!code-cs[UI_UserSettings_ToolsOptionPages#03](../extensibility/internals/codesnippet/CSharp/using-options-pages_3.cs)]
 [!code-vb[UI_UserSettings_ToolsOptionPages#03](../extensibility/internals/codesnippet/VisualBasic/using-options-pages_3.vb)]  
  
 자세한 내용은 [Controlling Options Settings](../Topic/Controlling%20Options%20Settings.md)을 참조하세요.  
  
## 옵션 페이지 설정 유지  
 IDE는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 자동화 모델을 완전히 지원하는 **옵션** 페이지의 상태 지속성을 구현합니다.  
  
 IDE에 포함된 페이지의 설정은 사용자가 **도구** 메뉴에서 **가져오기\/내보내기 설정** 명령을 클릭할 때 자동으로 저장되거나 검색됩니다.  
  
 HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\VisualStudio\\*\<VS 버전\>*\\AutomationProperties\(여기서 *\<VS 버전\>*은 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 릴리스의 버전 번호임\) 아래의 사용자 지정 **옵션** 페이지 레지스트리 항목에 `ProfileSave` 플래그를 추가하여 사용자 지정 **옵션** 페이지에서 이 자동 지속성 지원을 사용하도록 설정할 수 있습니다. 자세한 내용은 [사용자 지정 옵션 페이지 등록](../misc/registering-custom-options-pages.md)을 참조하세요.  
  
## 참고 항목  
 [Interop 어셈블리를 사용하여 옵션 페이지 만들기](../misc/creating-options-pages-by-using-interop-assemblies.md)   
 [옵션 페이지 만들기](../extensibility/internals/creating-options-pages.md)   
 [자동화를 사용하여 옵션 페이지 만들기](../misc/creating-options-pages-by-using-automation.md)   
 [Controlling Options Settings](../Topic/Controlling%20Options%20Settings.md)   
 [사용자 지정 옵션 페이지 등록](../misc/registering-custom-options-pages.md)   
 [옵션 페이지 열기](../misc/opening-an-options-page.md)   
 [확장 사용자 설정 및 옵션](../extensibility/extending-user-settings-and-options.md)