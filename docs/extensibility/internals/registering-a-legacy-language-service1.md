---
title: "레거시 언어 서비스를 등록 하는 중 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "등록 언어 서비스 [관리 되는 패키지 프레임 워크]"
ms.assetid: d33b08af-09e0-4c79-87b2-5536b27fbacf
caps.latest.revision: 22
caps.handback.revision: 22
ms.author: "gregvanl"
manager: "ghogen"
---
# 레거시 언어 서비스를 등록 하는 중
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

VSPackage에서 제공 되는 언어 서비스는 관리 되는 패키지 프레임 워크 \(MPF\)에서 \(참조 [Vspackage](../../extensibility/internals/vspackages.md)\)에 등록 된 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 레지스트리 키 및 항목을 추가 하 여 합니다. 부분적으로 설치 하는 동안 및 부분적으로 런타임에이 등록 과정에서 수행 됩니다.  
  
## 특성을 사용 하 여 언어 서비스를 등록 합니다.  
 다음과 같은 특성은 언어 서비스를 등록 하는 데 사용 됩니다.  
  
-   <xref:Microsoft.VisualStudio.Shell.ProvideServiceAttribute>  
  
-   <xref:Microsoft.VisualStudio.Shell.ProvideLanguageServiceAttribute>  
  
-   <xref:Microsoft.VisualStudio.Shell.ProvideLanguageExtensionAttribute>  
  
-   <xref:Microsoft.VisualStudio.Shell.ProvideLanguageCodeExpansionAttribute>  
  
-   <xref:Microsoft.VisualStudio.Shell.ProvideLanguageEditorOptionPageAttribute>  
  
 이러한 특성을 아래 설명  
  
### ProvideServiceAttribute  
 이 특성을 서비스로 언어 서비스를 등록합니다.  
  
### 예제  
  
```c#  
using Microsoft.VisualStudio.Shell;  
  
namespace TestLanguagePackage  
{  
    [ProvideServiceAttribute(typeof(TestLanguageService),  
                             ServiceName = "Test Language Service")]  
  
    public class TestLanguagePackage : Package  
    {  
    }  
}  
```  
  
### ProvideLanguageServiceAttribute  
 이 특성을 언어 서비스로 특히 언어 서비스를 등록합니다. 언어 서비스를 제공 하는 기능을 지정 하는 옵션을 설정할 수 있습니다. 이 예제에서는 언어 서비스가 제공할 수 있는 옵션의 하위 집합을 보여 줍니다. 언어 서비스 옵션의 전체 집합을 참조 하십시오. <xref:Microsoft.VisualStudio.Shell.ProvideLanguageServiceAttribute>합니다.  
  
### 예제  
  
```c#  
using Microsoft.VisualStudio.Shell;  
  
namespace TestLanguagePackage  
{  
    [ProvideLanguageServiceAttribute(typeof(TestLanguageService),  
                             "Test Language",  
                             106,             // resource ID of localized language name  
                             CodeSense = true,             // Supports IntelliSense  
                             RequestStockColors = false,   // Supplies custom colors  
                             EnableCommenting = true,      // Supports commenting out code  
                             EnableAsyncCompletion = true  // Supports background parsing  
                             )]  
  
    public class TestLanguagePackage : Package  
    {  
    }  
}  
```  
  
### ProvideLanguageExtensionAttribute  
 이 특성에는 파일 확장명을 가진 언어 서비스에 연결합니다. 모든 프로젝트에서 해당 확장명을 가진 파일 로드 될 때마다 언어 서비스를 시작 하며 파일의 내용을 표시 하는 데 사용 됩니다.  
  
### 예제  
  
```c#  
using Microsoft.VisualStudio.Shell;  
  
namespace TestLanguagePackage  
{  
    [ProvideLanguageExtensionAttribute(typeof(TestLanguageService),  
                                       ".Testext")]  
  
    public class TestLanguagePackage : Package  
    {  
    }  
}  
```  
  
### ProvideLanguageCodeExpansionAttribute  
 이 특성은 코드 확장 또는 조각 서식 파일을 가져온 위치를 등록 합니다. 이 정보를 사용 하 여는 **코드 조각 브라우저** 및 소스 파일에 코드 조각을 삽입 될 때 편집기에서.  
  
### 예제  
  
```c#  
using Microsoft.VisualStudio.Shell;  
  
namespace TestLanguagePackage  
{  
    [ProvideLanguageCodeExpansionAttribute(  
             typeof(TestLanguageService),  
             "Test Language", // Name of language used as registry key.  
             106,           // Resource ID of localized name of language service.  
             "testlanguage",  // language key used in snippet templates.  
             @"%InstallRoot%\Test Language\SnippetsIndex.xml",  // Path to snippets index  
             SearchPaths = @"%InstallRoot%\Test Language\Snippets\%LCID%\Snippets\;" +  
                           @"%TestDocs%\Code Snippets\Test Language\Test Code Snippets"  
             )]  
  
    public class TestLanguagePackage : Package  
    {  
    }  
}  
```  
  
### ProvideLanguageEditorOptionPageAttribute  
 이 특성에 표시 되는 속성 페이지를 등록 된 **옵션** 대화 상자는 **텍스트 편집기** 범주입니다. 언어 서비스에 대해 표시 될 각 페이지에 대 한 이러한 특성 중 하나를 사용 합니다. 트리 구조에서 페이지 구성 해야 할 경우 추가 특성을 사용 하 여 트리의 각 노드를 정의할 수 있습니다.  
  
### 예제  
 이 예제에서는 두 개의 속성 페이지를 보여 줍니다. **옵션** 및 **들여쓰기**, 및 두 번째 속성 페이지를 포함 하는 하나의 노드가 있습니다.  
  
```c#  
using Microsoft.VisualStudio.Shell;  
  
namespace TestLanguagePackage  
{  
    [ProvideLanguageEditorOptionPageAttribute(  
             "Test Language",  // Registry key name for language  
             "Options",      // Registry key name for property page  
             "#242",         // Localized name of property page  
             OptionPageGuid = "{A2FE74E1-FFFF-3311-4342-123052450768}"  // GUID of property page  
             )]  
    [ProvideLanguageEditorOptionPageAttribute(  
             "Test Language",  // Registry key name for language  
             "Advanced",     // Registry key name for node  
             "#243",         // Localized name of node  
             )]  
    [ProvideLanguageEditorOptionPageAttribute(  
             "Test Language",  // Registry key name for language  
             @"Advanced\Indenting",     // Registry key name for property page  
             "#244",         // Localized name of property page  
             OptionPageGuid = "{A2FE74E2-FFFF-3311-4342-123052450768}"  // GUID of property page  
             )]  
  
    public class TestLanguagePackage : Package  
    {  
    }  
}  
```  
  
## 런타임 시 언어 서비스 proffer  
 알려야 언어 패키지를 로드할 때 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 언어 서비스 준비 되었는지 확인 합니다. 서비스 proffering 하 여이 작업을 수행 합니다. 이 작업을 수행는 <xref:Microsoft.VisualStudio.Shell.Package.Initialize%2A> 메서드. 또한 백그라운드 구문 분석을 수행할 수 있습니다 하므로 유휴 기간 동안 언어 서비스를 호출 하는 타이머를 시작 해야 할 수도 있습니다. 이 유휴 타이머가 또한 문서 속성을 통해 모든를 구현한 경우 업데이트는 <xref:Microsoft.VisualStudio.Package.DocumentProperties> 클래스입니다. 타이머를 지원 하기 위해 패키지를 구현 해야는 <xref:Microsoft.VisualStudio.OLE.Interop.IOleComponent> 인터페이스 \(만 <xref:Microsoft.VisualStudio.OLE.Interop.IOleComponent.FDoIdle%2A> 메서드를 완벽 하 게 구현 해야 하 고 나머지 메서드는 기본 값을 반환할 수 있습니다\).  
  
### 예제  
 이 예제에서는 서비스 proffering 고 유휴 타이머가 제공 하는 일반적인 접근 방법을 보여 줍니다.  
  
```c#  
  
using System;  
using System.Runtime.InteropServices;  
using System.ComponentModel.Design;  
using Microsoft.VisualStudio.Package;  
using Microsoft.VisualStudio.Shell;  
using Microsoft.VisualStudio.OLE.Interop;  
using Microsoft.VisualStudio.TextManager.Interop;  
  
namespace TestLanguagePackage  
{  
    [Microsoft.VisualStudio.Shell.ProvideService(typeof(TestLanguageService))]  
    [Microsoft.VisualStudio.Shell.ProvideLanguageExtension(typeof(TestLanguageService), ".testext")]  
    [Microsoft.VisualStudio.Shell.ProvideLanguageService(typeof(TestLanguageService), "Test Language", 0,  
        AutoOutlining = true,  
        EnableCommenting = true,  
        MatchBraces = true,  
        ShowMatchingBrace = true)]  
    [Guid("00000000-0000-0000-0000-00000000000")] //provide a unique GUID for the package  
  
    public class TestLanguagePackage : Package, IOleComponent  
    {  
        private uint m_componentID;  
  
        protected override void Initialize()  
        {  
            base.Initialize();  // required  
  
            // Proffer the service.  
            IServiceContainer serviceContainer = this as IServiceContainer;  
            TestLanguageService langService      = new TestLanguageService();  
            langService.SetSite(this);  
            serviceContainer.AddService(typeof(TestLanguageService),  
                                        langService,  
                                        true);  
  
            // Register a timer to call our language service during  
            // idle periods.  
            IOleComponentManager mgr = GetService(typeof(SOleComponentManager))  
                                       as IOleComponentManager;  
            if (m_componentID == 0 && mgr != null)  
            {  
                OLECRINFO[] crinfo = new OLECRINFO[1];  
                crinfo[0].cbSize            = (uint)Marshal.SizeOf(typeof(OLECRINFO));  
                crinfo[0].grfcrf            = (uint)_OLECRF.olecrfNeedIdleTime |  
                                              (uint)_OLECRF.olecrfNeedPeriodicIdleTime;  
                crinfo[0].grfcadvf          = (uint)_OLECADVF.olecadvfModal     |  
                                              (uint)_OLECADVF.olecadvfRedrawOff |  
                                              (uint)_OLECADVF.olecadvfWarningsOff;  
                crinfo[0].uIdleTimeInterval = 1000;  
                int hr = mgr.FRegisterComponent(this, crinfo, out m_componentID);  
            }  
        }  
  
        protected override void Dispose(bool disposing)  
        {  
            if (m_componentID != 0)  
            {  
                IOleComponentManager mgr = GetService(typeof(SOleComponentManager))  
                                           as IOleComponentManager;  
                if (mgr != null)  
                {  
                    int hr = mgr.FRevokeComponent(m_componentID);  
                }  
                m_componentID = 0;  
            }  
  
            base.Dispose(disposing);  
        }  
  
        #region IOleComponent Members  
  
        public int FDoIdle(uint grfidlef)  
        {  
            bool bPeriodic = (grfidlef & (uint)_OLEIDLEF.oleidlefPeriodic) != 0;  
            // Use typeof(TestLanguageService) because we need to  
            // reference the GUID for our language service.  
            LanguageService service = GetService(typeof(TestLanguageService))  
                                      as LanguageService;  
            if (service != null)  
            {  
                service.OnIdle(bPeriodic);  
            }  
            return 0;  
        }  
  
        public int FContinueMessageLoop(uint uReason,  
                                        IntPtr pvLoopData,  
                                        MSG[] pMsgPeeked)  
        {  
            return 1;  
        }  
  
        public int FPreTranslateMessage(MSG[] pMsg)  
        {  
            return 0;  
        }  
  
        public int FQueryTerminate(int fPromptUser)  
        {  
            return 1;  
        }  
  
        public int FReserved1(uint dwReserved,  
                              uint message,  
                              IntPtr wParam,  
                              IntPtr lParam)  
        {  
            return 1;  
        }  
  
        public IntPtr HwndGetWindow(uint dwWhich, uint dwReserved)  
        {  
            return IntPtr.Zero;  
        }  
  
        public void OnActivationChange(IOleComponent pic,  
                                       int fSameComponent,  
                                       OLECRINFO[] pcrinfo,  
                                       int fHostIsActivating,  
                                       OLECHOSTINFO[] pchostinfo,  
                                       uint dwReserved)  
        {  
        }  
  
        public void OnAppActivate(int fActive, uint dwOtherThreadID)  
        {  
        }  
  
        public void OnEnterState(uint uStateID, int fEnter)  
        {  
        }  
  
        public void OnLoseActivation()  
        {  
        }  
  
        public void Terminate()  
        {  
        }  
  
        #endregion  
    }  
}   
```