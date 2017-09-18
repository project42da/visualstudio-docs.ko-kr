---
title: "Vspackage를 로드합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Vspackage를 자동 로드"
  - "VSPackage, 로드"
ms.assetid: f4c3dcea-5051-4065-898f-601269649d92
caps.latest.revision: 17
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 17
---
# Vspackage를 로드합니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

해당 기능이 필요할 때에 Vspackage Visual Studio에 로드 됩니다. 예를 들어 Visual Studio 프로젝트 팩터리 또는 VSPackage 구현 하는 서비스를 사용 하는 경우 VSPackage 로드 됩니다. 이 기능은 성능 향상을 위해 가능 하면 사용 되는 지연된 로드를 라고 합니다.  
  
> [!NOTE]
>  Visual Studio에서 VSPackage를 로드 하지 않고, VSPackage에서 제공 하는 명령 등과 같이 특정 VSPackage 정보를 확인할 수 있습니다.  
  
 Vspackage 설정할 수 있습니다 특정 사용자 인터페이스 \(UI\) 컨텍스트에서 자동 로드를 예를 들어, 솔루션을 엽니다.<xref:Microsoft.VisualStudio.Shell.ProvideAutoLoadAttribute> 특성이이 컨텍스트를 설정 합니다.  
  
### 특정 컨텍스트에서 VSPackage 자동 로드  
  
-   추가 된 `ProvideAutoLoad` VSPackage 특성에 특성:  
  
    ```c#  
    [DefaultRegistryRoot(@"Software\Microsoft\VisualStudio\14.0")]  
    [PackageRegistration(UseManagedResourcesOnly = true)]  
    [ProvideAutoLoad(UIContextGuids80.SolutionExists)]  
    [Guid("00000000-0000-0000-0000-000000000000")] // your specific package GUID  
    public class MyAutoloadedPackage : Package  
    {. . .}  
    ```  
  
     열거 된 필드를 참조 하십시오. <xref:Microsoft.VisualStudio.Shell.Interop.UIContextGuids80> UI 컨텍스트 및 GUID 값의 목록에 대 한 합니다.  
  
-   중단점을 설정 된 <xref:Microsoft.VisualStudio.Shell.Package.Initialize%2A> 메서드.  
  
-   VSPackage를 빌드하고 디버깅을 시작 합니다.  
  
-   솔루션을 로드 하거나 만드십시오.  
  
     VSPackage 로드 하 고 중단점에서 중지 합니다.  
  
## 로드 된 VSPackage를 강제 적용  
 일부 환경에서 VSPackage 강제로 다른 VSPackage 로드 되도록 할 수 있습니다. 예를 들어, 간단한 VSPackage를 CMDUIContext으로 제공 되지 않는 컨텍스트에서 더 큰 VSPackage를 로드할 수 있습니다.  
  
 사용할 수는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsShell.LoadPackage%2A> 메서드를 VSPackage를 로드 합니다.  
  
-   에이 코드를 삽입은 <xref:Microsoft.VisualStudio.Shell.Package.Initialize%2A> vspackage를 로드 하는 다른 VSPackage를 강제로 실행 하는 방법:  
  
    ```c#  
    IVsShell shell = GetService(typeof(SVsShell)) as IVsShell;  
    if (shell == null) return;  
  
    IVsPackage package = null;  
    Guid PackageToBeLoadedGuid =   
        new Guid(Microsoft.PackageToBeLoaded.GuidList.guidPackageToBeLoadedPkgString);  
    shell.LoadPackage(ref PackageToBeLoadedGuid, out package);  
  
    ```  
  
     강제로 VSPackage를 초기화할 때 `PackageToBeLoaded` 를 로드 합니다.  
  
     강제 로드 VSPackage 통신에 쓰일 수 없습니다. 대신 [사용 하 고 서비스를 제공 합니다.](../extensibility/using-and-providing-services.md)를 사용하세요.  
  
## 사용자 지정 특성을 사용 하 여 VSPackage를 등록 하려면  
 특정 한 경우 확장 프로그램에 대 한 새 등록 속성을 작성 해야 합니다. 새 레지스트리 키를 추가 하거나 기존 키를 새 값을 추가 하려면 등록 특성을 사용할 수 있습니다. 새 특성에서 파생 되어야 <xref:Microsoft.VisualStudio.Shell.RegistrationAttribute>, 를 재정의 해야 하 고는 <xref:Microsoft.VisualStudio.Shell.RegistrationAttribute.Register%2A> 및 <xref:Microsoft.VisualStudio.Shell.RegistrationAttribute.Unregister%2A> 메서드.  
  
## 레지스트리 키 만들기  
 다음 코드에서는 사용자 지정 특성을 만듭니다는 **사용자 지정** 등록 되는 VSPackage에 대 한 키 아래의 하위 키입니다.  
  
```c#  
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
  
## 기존 레지스트리 키 아래에 새 값 만들기  
 기존 키를 사용자 지정 값을 추가할 수 있습니다. 다음 코드를 VSPackage 등록 키를 새 값을 추가 하는 방법을 보여 줍니다.  
  
```c#  
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
  
## 참고 항목  
 [Vspackage](../extensibility/internals/vspackages.md)