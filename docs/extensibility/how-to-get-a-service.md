---
title: "방법: 서비스 가져오기 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "서비스를 사용"
ms.assetid: 1f000020-8fb7-4e39-8e1e-2e38c7fec3d4
caps.latest.revision: 20
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 20
---
# 방법: 서비스 가져오기
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

다른 기능에 액세스 하려면 Visual Studio 서비스 해야 하는 경우가 많습니다. 일반적으로 Visual Studio 서비스는 사용할 수 있는 하나 이상의 인터페이스를 제공 합니다. VSPackage에서 대부분의 서비스를 가져올 수 있습니다.  
  
 파생 된 모든 VSPackage <xref:Microsoft.VisualStudio.Shell.Package> 하는 요소가 잘못 배치 된 및 모든 글로벌 서비스에 요청할 수 있습니다. 패키지 클래스를 구현 하므로 <xref:System.IServiceProvider>, 모든 VSPackage 패키지에서 파생 되는 서비스 공급자 이기도 합니다.  
  
 Visual Studio 로드 될 때 한 <xref:Microsoft.VisualStudio.Shell.Package>, 전달는 <xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider> 개체는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.SetSite%2A> 초기화 하는 동안 메서드. 이 이라고 *사이 팅* VSPackage 합니다. 패키지 클래스는이 서비스 공급자를 배치 하 고 제공 된 <xref:Microsoft.VisualStudio.Shell.Package.GetService%2A> 서비스를 가져오기 위한 방법입니다.  
  
## 초기화는 VSPackage에서 서비스 가져오기  
  
1.  모든 Visual Studio 확장 확장 자산을 포함 하는 VSIX 배포 프로젝트를 시작 합니다. 만들기는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 라는 VSIX 프로젝트 `GetServiceExtension`합니다. VSIX 프로젝트 템플릿을 찾을 수는 **새 프로젝트** 대화 상자의 **Visual C\# \/ 확장성**합니다.  
  
2.  이제 사용자 지정 명령 항목 템플릿을 추가 **GetServiceCommand**합니다. 에 **새 항목 추가** 대화 상자에서 이동 **Visual C\# \/ 확장성** 선택한 **사용자 지정 명령**합니다. 에 **이름** 창의 맨 아래에 필드, 명령 파일 이름을 **GetServiceCommand.cs**합니다. 사용자 지정 명령을 만드는 방법에 대 한 자세한 내용은 [메뉴 명령을 사용 하 여 확장 만들기](../extensibility/creating-an-extension-with-a-menu-command.md)  
  
3.  GetServiceCommand.cs, MenuItemCommand 메서드의 본문을 제거 하 고 다음 코드를 추가 합니다.  
  
    ```c#  
    IVsActivityLog activityLog = ServiceProvider.GetService(typeof(SVsActivityLog)) as IVsActivityLog; if (activityLog == null) return; System.Windows.Forms.MessageBox.Show("Found the activity log service.");  
  
    ```  
  
     이 코드는 SVsActivityLog 서비스를 가져오고으로 캐스팅 한 <xref:Microsoft.VisualStudio.Shell.Interop.IVsActivityLog> 활동 로그에 쓰는 데 사용할 수 있는 인터페이스입니다. 예제를 보려면 [방법: 작업 로그를 사용 하 여](../extensibility/how-to-use-the-activity-log.md)를 참조하십시오.  
  
4.  프로젝트를 빌드하고 디버깅을 시작합니다. 실험적 인스턴스가 표시 됩니다.  
  
5.  실험적 인스턴스에서의 도구 메뉴에서 찾을 **호출 GetServiceCommand** 단추입니다. 이 단추를 클릭 하면 알리는 메시지 상자가 표시 됩니다 **활동 로그 서비스를 찾을 수 있습니다.**  
  
## 도구 창 또는 컨트롤 컨테이너에서 서비스 가져오기  
 때로는 도구 창에서 서비스 가져오기 또는 배치 되지 않습니다. 그렇지 않으면 원하는 서비스에 대해 알지 못하는 서비스 공급자와 요소가 배치 된 컨테이너를 제어 해야 합니다. 예를 들어 다음 컨트롤 내에서 작업 로그를 작성 하는 것이 좋습니다.  
  
 정적 <xref:Microsoft.VisualStudio.Shell.Package.GetGlobalService%2A> 방법은에서 파생 된 모든 VSPackage 처음으로 초기화 되는 캐시 된 서비스 공급자에 의존 <xref:Microsoft.VisualStudio.Shell.Package> 배치 됩니다.  
  
 VSPackage을 배치하기 전에 VSPackage 생성자를 호출 하기 때문에 글로벌 서비스를 VSPackage 생성자 내에서 일반적으로 사용할 수 없습니다. 참조 [방법: 서비스 문제 해결](../extensibility/how-to-troubleshoot-services.md) 해결 방법에 대 한 합니다.  
  
 도구 창 또는 다른 비 VSPackage 요소에는 서비스를 구입 하는 방법의 예를 들면 다음과 같습니다.  
  
```c#  
IVsActivityLog log = Package.GetGlobalService(typeof(SVsActivityLog)) as IVsActivityLog; if (log == null) return;  
```  
  
## DTE 개체에서 서비스 가져오기  
 서비스를 가져올 수도 있습니다 <xref:EnvDTE.DTEClass> 개체입니다. 그러나 가져와야 DTE 개체를 서비스로 VSPackage 호출 하거나 정적 <xref:Microsoft.VisualStudio.Shell.Package.GetGlobalService%2A> 메서드.  
  
 DTE 개체에서 <xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider>, 사용할 수 있는 쿼리를 사용 하 여 서비스에 대 한 <xref:Microsoft.VisualStudio.Shell.ServiceProvider.GetService%2A>합니다.  
  
 DTE 개체에서 서비스를 가져오는 방법은 다음과 같습니다.  
  
```c#  
// Start with the DTE object, for example: // using EnvDTE; // DTE dte = (DTE)GetService(typeof(DTE)); ServiceProvider sp = new ServiceProvider((Microsoft.VisualStudio.OLE.Interop.IServiceProvider)dte); if (sp != null) { IVsActivityLog log = sp.GetService(typeof(SVsActivityLog)) as IVsActivityLog; if (log != null) { System.Windows.Forms.MessageBox.Show("Found the activity log service."); } }  
```  
  
## 참고 항목  
 [방법: 서비스를 제공 합니다.](../extensibility/how-to-provide-a-service.md)   
 [사용 하 고 서비스를 제공 합니다.](../extensibility/using-and-providing-services.md)   
 [서비스 Essentials](../extensibility/internals/service-essentials.md)