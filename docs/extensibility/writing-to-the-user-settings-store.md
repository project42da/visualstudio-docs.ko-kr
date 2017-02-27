---
title: "사용자 설정 저장소에 쓰기 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: efd27f00-7fe5-45f8-9b97-371af732be97
caps.latest.revision: 3
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 3
---
# 사용자 설정 저장소에 쓰기
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

사용자 설정은에서 것과 같은 쓰기 가능한 설정의 **도구 \/ 옵션** 대화 상자, 속성 창 및 기타 특정 대화 상자입니다. Visual Studio 확장 적은 양의 데이터를 저장 하려면이 사용할 수 있습니다. 이 연습에서는 메모장에서 읽고 써서 사용자 설정 저장소에는 외부 도구와 Visual Studio에 추가 하는 방법을 보여 줍니다.  
  
### 사용자 설정 백업  
  
1.  디버깅 하 고 절차를 반복 수 있도록 외부 도구 설정을 다시 설정 수 있어야 합니다. 이 위해 필요에 따라 복원할 수 있도록 원래 설정을 저장 해야 합니다.  
  
2.  Regedit.exe를 엽니다.  
  
3.  HKEY\_CURRENT\_USER\\Software\\Microsoft\\VisualStudio\\14.0Exp\\External 도구 \\로 이동 합니다.  
  
    > [!NOTE]
    >  \\14.0Exp\\ 및 하지 \\14.0\\를 포함 하는 키에서 찾으려는 있는지 확인 합니다. Visual Studio의 실험적 인스턴스를 실행 하면 "14.0Exp" 레지스트리 하이브에 사용자 설정 됩니다.  
  
4.  \\External Tools\\ 하위 키를 마우스 오른쪽 단추로 누른 **내보내기**합니다. 다음 사항을 확인 **선택한 분기** 을 선택 합니다.  
  
5.  결과 외부 Tools.reg 파일을 저장 합니다.  
  
6.  외부 도구 설정을 다시 설정 하려는 경우 HKEY\_CURRENT\_USER\\Software\\Microsoft\\VisualStudio\\14.0Exp\\External 도구 \\ 레지스트리 키를 선택 하 고 클릭 나중 **삭제** 상황에 맞는 메뉴에 있습니다.  
  
7.  경우는 **키 삭제 확인** 대화 상자가 나타나면 클릭 **예**합니다.  
  
8.  이전에 저장 하는 외부 Tools.reg 파일을 마우스 오른쪽 단추로 클릭 합니다. **로 열기**, 를 클릭 하 고 **레지스트리 편집기**합니다.  
  
## 사용자 설정 저장소에 쓰기  
  
1.  UserSettingsStoreExtension 라는 VSIX 프로젝트를 하 고 UserSettingsStoreCommand 라는 사용자 지정 명령을 추가 합니다. 사용자 지정 명령을 만드는 방법에 대 한 자세한 내용은 참조 하십시오. [메뉴 명령을 사용 하 여 확장 만들기](../extensibility/creating-an-extension-with-a-menu-command.md)  
  
2.  UserSettingsStoreCommand.cs에서 다음 추가 문을 사용 하 여:  
  
    ```c#  
    using System.Collections.Generic; using Microsoft.VisualStudio.Settings; using Microsoft.VisualStudio.Shell.Settings;  
    ```  
  
3.  MenuItemCallback, 메서드의 본문을 삭제 하 고 다음과 같이 설정 저장 사용자 가져오기:  
  
    ```c#  
    private void MenuItemCallback(object sender, EventArgs e) { SettingsManager settingsManager = new ShellSettingsManager(ServiceProvider); WritableSettingsStore userSettingsStore = settingsManager.GetWritableSettingsStore(SettingsScope.UserSettings); }  
    ```  
  
4.  이제 메모장 외부 도구로 이미 설정 되어 있는지 알아보십시오. 인지 확인 하기 위해 ToolCmd 설정을 "Notepad" 다음과 같이 모든 외부 도구를 반복 해야 합니다.  
  
    ```c#  
    private void MenuItemCallback(object sender, EventArgs e) { SettingsManager settingsManager = new ShellSettingsManager(ServiceProvider); WritableSettingsStore userSettingsStore = settingsManager.GetWritableSettingsStore(SettingsScope.UserSettings); // Find out whether Notepad is already an External Tool. int toolCount = userSettingsStore.GetInt32("External Tools", "ToolNumKeys"); bool hasNotepad = false; CompareInfo Compare = CultureInfo.InvariantCulture.CompareInfo; for (int i = 0; i < toolCount; i++) { if (Compare.IndexOf(userSettingsStore.GetString("External Tools", "ToolCmd" + i), "Notepad", CompareOptions.IgnoreCase) >= 0) { hasNotepad = true; break; } } }  
  
    ```  
  
5.  메모장으로 외부 도구 설정 되지 않은 경우 설정 다음과 같이 합니다.  
  
    ```vb  
    private void MenuItemCallback(object sender, EventArgs e) { SettingsManager settingsManager = new ShellSettingsManager(ServiceProvider); WritableSettingsStore userSettingsStore = settingsManager.GetWritableSettingsStore(SettingsScope.UserSettings); // Find out whether Notepad is already installed. int toolCount = userSettingsStore.GetInt32("External Tools", "ToolNumKeys"); bool hasNotepad = false; CompareInfo Compare = CultureInfo.InvariantCulture.CompareInfo; for (int i = 0; i < toolCount; i++) { if (Compare.IndexOf(userSettingsStore.GetString("External Tools", "ToolCmd" + i), "Notepad", CompareOptions.IgnoreCase) >= 0) { hasNotepad = true; break; } } string message = (hasNotepad) ? "Notepad already installed" : "Installing Notepad"; if (!hasNotepad) { userSettingsStore.SetString("External Tools", "ToolTitle" + toolCount, "&Notepad"); userSettingsStore.SetString("External Tools", "ToolCmd" + toolCount, "C:\\Windows\\notepad.exe"); userSettingsStore.SetString("External Tools", "ToolArg" + toolCount, ""); userSettingsStore.SetString("External Tools", "ToolDir" + toolCount, "$(ProjectDir)"); userSettingsStore.SetString("External Tools", "ToolSourceKey" + toolCount, ""); userSettingsStore.SetUInt32("External Tools", "ToolOpt" + toolCount, 0x00000011); userSettingsStore.SetInt32("External Tools", "ToolNumKeys", toolCount + 1); } }  
    ```  
  
6.  코드를 테스트 합니다. 추가 메모장으로 외부 도구를 롤백해야 레지스트리를 두 번째로 실행 하기 전에 해야 합니다.  
  
7.  코드를 빌드하고 디버깅을 시작 합니다.  
  
8.  에 **도구** 메뉴를 클릭 하 여 **UserSettingsStoreCommand 호출**합니다. 메모장에 추가 된 **도구** 메뉴.  
  
9. 이제 메모장에 표시 하는 도구 \/ 옵션 메뉴를 클릭 하 **메모장** 메모장의 인스턴스를 준비 해야 합니다.