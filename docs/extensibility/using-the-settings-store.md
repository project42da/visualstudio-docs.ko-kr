---
title: "설정 저장소를 사용 하 여 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "설정 저장소를 사용 하 여"
ms.assetid: 447ec08a-eca5-40b8-89b0-f98fdf3d39a4
caps.latest.revision: 28
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 28
---
# 설정 저장소를 사용 하 여
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

설정 저장소는 다음과 같은 두 종류가 있습니다.  
  
-   구성 설정\-Visual Studio 및 VSPackage 설정이 읽기 전용입니다. Visual Studio는이 저장소에 모든 알려진된.pkgdef 파일에서 설정을 병합합니다.  
  
-   쓰기 가능한 설정의 페이지에 표시 되는 것과 같은 사용자 설정의 **옵션** 대화 상자, 속성 페이지와 다른 대화 상자에 특정 합니다. Visual Studio 확장에는 적은 양의 데이터의 로컬 저장소에 대 한 이러한 사용할 수 있습니다.  
  
 이 연습에는 구성 설정 저장소에서 데이터를 읽는 방법을 보여 줍니다. 참조 [사용자 설정 저장소에 쓰기](../extensibility/writing-to-the-user-settings-store.md) 에 대 한 설명은 사용자 설정 저장소에 쓰는 방법입니다.  
  
## 예제 프로젝트 만들기  
 이 섹션에는 데모에 대 한 메뉴 명령을 사용 하 여 간단한 확장 프로젝트를 만드는 방법을 보여 줍니다.  
  
1.  모든 Visual Studio 확장 확장 자산을 포함 하는 VSIX 배포 프로젝트를 시작 합니다. 만들기는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 라는 VSIX 프로젝트 `SettingsStoreExtension`합니다. VSIX 프로젝트 템플릿을 찾을 수는 **새 프로젝트** 대화 상자의 **Visual C\# \/ 확장성**합니다.  
  
2.  이제 사용자 지정 명령 항목 템플릿을 추가 **SettingsStoreCommand**합니다. 에 **새 항목 추가** 대화 상자에서 이동 **Visual C\# \/ 확장성** 선택한 **사용자 지정 명령**합니다. 에 **이름** 창의 맨 아래에 필드, 명령 파일 이름을 **SettingsStoreCommand.cs**합니다. 사용자 지정 명령을 만드는 방법에 대 한 자세한 내용은 참조 하십시오. [메뉴 명령을 사용 하 여 확장 만들기](../extensibility/creating-an-extension-with-a-menu-command.md)  
  
## 구성 설정 저장소를 사용 하 여  
 이 섹션에는 검색 및 구성 설정을 표시 하는 방법을 보여 줍니다.  
  
1.  SettingsStorageCommand.cs 파일에서 다음 추가 문을 사용 하 여:  
  
    ```  
    using System.Collections.Generic; using Microsoft.VisualStudio.Settings; using Microsoft.VisualStudio.Shell.Settings; using System.Windows.Forms;  
    ```  
  
2.  `MenuItemCallback`, 메서드의 본문을 제거 하 고 구성 설정 저장소를 가져오는 다음이 줄을 추가 합니다.  
  
    ```  
    SettingsManager settingsManager = new ShellSettingsManager(ServiceProvider); SettingsStore configurationSettingsStore = settingsManager.GetReadOnlySettingsStore(SettingsScope.Configuration);  
    ```  
  
     <xref:Microsoft.VisualStudio.Shell.Settings.ShellSettingsManager> 는 통해 관리 되는 도우미 클래스는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSettingsManager> 서비스입니다.  
  
3.  이제 Windows Phone 도구가 설치 되어 있는지 알아보십시오. 코드는 다음과 같습니다.  
  
    ```  
    private void MenuItemCallback(object sender, EventArgs e) { SettingsManager settingsManager = new ShellSettingsManager(ServiceProvider); SettingsStore configurationSettingsStore = settingsManager.GetReadOnlySettingsStore(SettingsScope.Configuration); bool arePhoneToolsInstalled = configurationSettingsStore.CollectionExists(@"InstalledProducts\Microsoft Windows Phone Developer Tools"); string message = "Microsoft Windows Phone Developer Tools: " + arePhoneToolsInstalled; MessageBox.Show(message); }  
    ```  
  
4.  코드를 테스트 합니다. 프로젝트를 빌드하고 디버깅을 시작합니다.  
  
5.  실험적 인스턴스에서는 **도구** 메뉴를 클릭 하 여 **SettingsStoreCommand 호출**합니다.  
  
     메시지 상자 말하기가 나타납니다 **Microsoft Windows Phone 개발자 도구:**  뒤 **True** 또는 **False**합니다.  
  
 Visual Studio의 시스템 레지스트리에 있는 설정 저장소를 유지합니다.  
  
#### 레지스트리 편집기를 사용 하 여 구성 설정을 확인 하려면  
  
1.  Regedit.exe를 엽니다.  
  
2.  HKEY\_CURRENT\_USER\\Software\\Microsoft\\VisualStudio\\14.0Exp\_Config\\InstalledProducts\\로 이동 합니다.  
  
    > [!NOTE]
    >  \\14.0Exp\_Config\\ 및 하지 \\14.0\_Config\\를 포함 하는 키에서 찾으려는 있는지 확인 합니다. Visual Studio의 실험적 인스턴스를 실행 하면 구성 설정은 레지스트리 하이브 "14.0Exp\_Config"에 있습니다.  
  
3.  \\Installed Products\\ 노드를 확장 합니다. 이전 단계에서 메시지의 경우 **Microsoft Windows Phone 개발자 도구 설치: True**, \\Installed Products\\ Microsoft Windows Phone 개발자 도구 노드를 포함 해야 합니다. 메시지의 경우 **Microsoft Windows Phone 개발자 도구 설치: False**, \\Installed Products\\ Microsoft Windows Phone 개발자 도구 노드 없어야 합니다.