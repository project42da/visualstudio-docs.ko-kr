---
title: "Interop 어셈블리 명령 처리기를 등록 하는 중 | Microsoft Docs"
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
  - "interop 어셈블리, 명령 처리기"
  - "등록 하는 interop 어셈블리를 처리 하는 명령"
ms.assetid: 303cd399-e29d-4ea1-8abe-5e0b59c12a0c
caps.latest.revision: 19
caps.handback.revision: 19
ms.author: "gregvanl"
manager: "ghogen"
---
# Interop 어셈블리 명령 처리기를 등록 하는 중
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

VSPackage를 등록 해야 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 통합된 개발 환경 \(IDE\)는 해당 명령을 제대로 라우팅되도록 되도록 합니다.  
  
 수동 편집 하거나 등록자 \(.rgs\) 파일을 사용 하 여 레지스트리를 업데이트할 수 있습니다. 자세한 내용은 [Creating Registrar Scripts](/visual-cpp/atl/creating-registrar-scripts)을 참조하세요.  
  
 통해이 기능을 제공 하는 관리 되는 패키지 프레임 워크 \(MPF\)는 <xref:Microsoft.VisualStudio.Shell.ProvideMenuResourceAttribute> 클래스입니다.  
  
 [Command Table Format Reference](http://msdn.microsoft.com/ko-kr/09e9c6ef-9863-48de-9483-d45b7b7c798f) 리소스는 관리 되지 않는 위성 dll UI에에서 있습니다.  
  
## Vspackage 명령 처리기 등록  
 사용자 인터페이스 \(UI\)에 대 한 처리기 역할을 VSPackage\-기반된 명령을 VSPackage 후 레지스트리 항목이 필요 `GUID`합니다. 이 레지스트리 항목 VSPackage의 UI 리소스 파일과 해당 파일 내에서 메뉴 리소스의 위치를 지정 합니다. 자체 레지스트리 항목 HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\VisualStudio\\ 아래에 있는*\< 버전 \>*\\Menus, 여기서 *\< 버전 \>* 버전인 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], 9.0 예를 들어.  
  
> [!NOTE]
>  HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\VisualStudio\\의 루트 경로*\< 버전 \>* 대체도 재정의할 수 때 루트는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 셸 초기화 됩니다. 루트 경로 대 한 자세한 내용은 참조 [Windows Installer를 사용 하 여 Vspackage를 설치](../../extensibility/internals/installing-vspackages-with-windows-installer.md)합니다.  
  
### CTMENU 리소스 레지스트리 항목  
 레지스트리 항목의 구조는 같습니다.  
  
```  
HKEY_LOCAL_MACHINE\Software\VisualStudio\<Version>\ Menus\ <GUID> = <Resource Information>  
```  
  
 \<*GUID*\>은 `GUID` vspackage {XXXXXX\-XXXX\-XXXX\-XXXX\-XXXXXXXXX} 형식에서입니다.  
  
 *\< 리소스 정보 \>* 쉼표로 구분 된 세 가지 요소로 구성 됩니다. 이러한 요소는 순서에서는:  
  
 \<*리소스 DLL에 대 한 경로*\>, \<*메뉴 리소스 ID*\>, \<*메뉴 버전*\>  
  
 다음 표에서 설명의 필드 \<*리소스 정보*\>입니다.  
  
|요소|설명|  
|--------|--------|  
|\<*리소스 DLL에 대 한 경로*\>|이 리소스는 메뉴 리소스를 포함 하는 DLL로의 전체 경로 또는이 공백으로 VSPackage의 리소스 DLL 임을 나타내는 데 사용할 남아 \(VSPackage 자체 등록 되어 있는 패키지 하위 키에 지정 된 대로\).<br /><br /> 이에이 필드를 비워 둡니다.|  
|\<*메뉴 리소스 ID*\>|리소스 id는 `CTMENU` 에서 컴파일된 VSPackage에 대 한 모든 UI 요소를 포함 하는 리소스는 [.vsct](../../extensibility/internals/visual-studio-command-table-dot-vsct-files.md) 파일입니다.|  
|\<*메뉴 버전*\>|이에 대 한 버전으로 사용 되는 숫자는 `CTMENU` 리소스입니다.[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 이 값을 사용 하 여 내용을 remerge 해야 하는지 결정 하는 `CTMENU` 모든 캐시를 사용 하 여 리소스 `CTMENU` 리소스입니다. remerge devenv 설치 명령을 실행 하 여 트리거됩니다.<br /><br /> 이 값을 1로 설정 되 고 후 변경 될 때마다 증가 처음 해야는 `CTMENU` 리소스는 remerge 발생 하기 전에 하 고 있습니다.|  
  
### 예제  
 몇 가지 리소스 항목의 예는 다음과 같습니다.  
  
```  
HKEY_LOCAL_MACHINE\Software\VisualStudio\9.0Exp\ Menus\ {019971D6-4685-11D2-B48A-0000F87572EB} = ,1, 10 {1b027a40-8f43-11d0-8d11-00a0c91bc942} = , 10211, 3  
```  
  
## 참고 항목  
 [Vspackage에서 사용자 인터페이스 요소를 추가 하는 방법](../../extensibility/internals/how-vspackages-add-user-interface-elements.md)   
 [명령 및 Interop 어셈블리를 사용 하는 메뉴](../../extensibility/internals/commands-and-menus-that-use-interop-assemblies.md)