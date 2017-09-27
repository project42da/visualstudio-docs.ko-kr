---
title: "등록 및 Vspackage 등록 취소 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- registration, VSPackages
- VSPackages, registering
ms.assetid: e25e7a46-6a55-4726-8def-ca316f553d6b
caps.latest.revision: 35
ms.author: gregvanl
manager: ghogen
translation.priority.mt:
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
ms.translationtype: MT
ms.sourcegitcommit: 4a36302d80f4bc397128e3838c9abf858a0b5fe8
ms.openlocfilehash: 312c06295492ac9bd1136ea7de9a0399f247c365
ms.contentlocale: ko-kr
ms.lasthandoff: 09/26/2017

---
# <a name="registering-and-unregistering-vspackages"></a>Vspackage를 등록 및 등록 취소
특성을 사용 하 여 VSPackage를 등록 하지만  
  
## <a name="registering-a-vspackage"></a>VSPackage를 등록 하는 중  
 관리 되는 Vspackage의 등록을 제어 하는 특성을 사용할 수 있습니다. 모든 등록 정보는.pkgdef 파일에 포함 됩니다. 파일 기반 등록에 대 한 자세한 내용은 참조 하십시오. [CreatePkgDef 유틸리티](../extensibility/internals/createpkgdef-utility.md)합니다.  
  
 다음 코드에는 VSPackage를 등록 하 여 표준 등록 특성을 사용 하는 방법을 보여 줍니다.  
  
```csharp  
[PackageRegistration(UseManagedResourcesOnly = true)]  
[Guid("0B81D86C-0A85-4f30-9B26-DD2616447F95")]  
public sealed class BasicPackage : Package  
{. . .}  
```  
  
## <a name="unregistering-an-extension"></a>확장 등록 취소  
 다른 Vspackage 많이 실험 된 실험적 인스턴스에서에서 제거 하려는 하는 경우 실행 하기만 하면는 **재설정** 명령입니다. 검색할 **Visual Studio 실험적 인스턴스 다시 설정** 컴퓨터의 시작 페이지에서 또는 명령줄에서이 명령을 실행:  
  
```vb  
<location of Visual Studio 2015 install>\"Microsoft Visual Studio 14.0\VSSDK\VisualStudioIntegration\Tools\Bin\CreateExpInstance.exe" /Reset /VSInstance=14.0 /RootSuffix=Exp  
```  
  
 로 이동 하는 사용자가 설치한 Visual Studio의 개발 인스턴스에서 확장을 제거 하려는 경우 **도구 / 확장명 및 업데이트**확장을 찾아 클릭 **제거**합니다.  
  
 몇 가지 이유로 이러한 메서드의 둘 다 확장에 성공 하면 명령줄에서 VSPackage 어셈블리를 다음과 같이 등록 취소할 수 있습니다.  
  
```  
<location of Visual Studio 2015 install>\"Microsoft Visual Studio 14.0\VSSDK\VisualStudioIntegration\Tools\Bin\regpkg" /unregister <pathToVSPackage assembly>  
```  
  
<a name="using-a-custom-registration-attribute-to-register-an-extension"></a>  
  
## <a name="use-a-custom-registration-attribute-to-register-an-extension"></a>사용자 지정 등록 특성을 사용 하 여 확장을 등록 하려면  
  
특정 한 경우에 확장 프로그램에 대해 새 등록 특성을 만들려면 할 수 있습니다. 새 레지스트리 키를 추가 하거나 기존 키를 새 값을 추가 하려면 등록 특성을 사용할 수 있습니다. 새 특성에서 파생 되어야 <xref:Microsoft.VisualStudio.Shell.RegistrationAttribute>를 재정의 해야 하 고는 <xref:Microsoft.VisualStudio.Shell.RegistrationAttribute.Register%2A> 및 <xref:Microsoft.VisualStudio.Shell.RegistrationAttribute.Unregister%2A> 메서드.  
  
### <a name="creating-a-custom-attribute"></a>사용자 지정 특성 만들기  
  
다음 코드에는 새 등록 특성을 만드는 방법을 보여 줍니다.  
  
```csharp  
[AttributeUsage(AttributeTargets.Class, Inherited = true, AllowMultiple = false)]  
    public class CustomRegistrationAttribute : RegistrationAttribute  
    {  
    }  
```  
  
 <xref:System.AttributeUsageAttribute> 특성 클래스에 하 고 그 사용할 수 있는지 여부 두 번 이상을 상속할 수 있는지 여부는 특성 관계가 있는 프로그램 요소 (클래스, 메서드, 등)를 지정 하는 데 사용 됩니다.  
  
### <a name="creating-a-registry-key"></a>레지스트리 키 만들기  
  
다음 코드에서 사용자 지정 특성을 만듭니다는 **사용자 지정** 등록 되는 VSPackage에 대 한 키 아래 하위 키입니다.  
  
```csharp  
public override void Register(RegistrationAttribute.RegistrationContext context)  
{  
    Key packageKey = null;  
    try  
    {   
        packageKey = context.CreateKey(@"Packages\{" + context.ComponentType.GUID + @"}\Custom");  
        packageKey.SetValue("NewCustom", 1);  
    }  
    finally  
    {  
        if (packageKey != null)  
            packageKey.Close();  
    }  
}  
  
public override void Unregister(RegistrationContext context)  
{  
    context.RemoveKey(@"Packages\" + context.ComponentType.GUID + @"}\Custom");  
}  
```  
  
### <a name="creating-a-new-value-under-an-existing-registry-key"></a>기존 레지스트리 키 아래에서 새 값 만들기  
  
기존 키를 사용자 지정 값을 추가할 수 있습니다. 다음 코드에는 VSPackage 등록 키를 새 값을 추가 하는 방법을 보여 줍니다.  
  
```csharp  
public override void Register(RegistrationAttribute.RegistrationContext context)  
{  
    Key packageKey = null;  
    try  
    {   
        packageKey = context.CreateKey(@"Packages\{" + context.ComponentType.GUID + "}");  
        packageKey.SetValue("NewCustom", 1);  
    }  
    finally  
    {  
        if (packageKey != null)  
            packageKey.Close();  
                }  
}  
  
public override void Unregister(RegistrationContext context)  
{  
    context.RemoveValue(@"Packages\" + context.ComponentType.GUID, "NewCustom");  
}  
```
  
## <a name="see-also"></a>참고 항목  
 [VSPackage](../extensibility/internals/vspackages.md)
