---
title: "사용자 설정 저장소에 쓰기 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: efd27f00-7fe5-45f8-9b97-371af732be97
caps.latest.revision: "3"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: a461a255920cc8a01282d2c93b9ba7fd5b38df75
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="writing-to-the-user-settings-store"></a>사용자 설정 저장소에 쓰기
사용자 설정은 같은 쓰기 가능 설정이 **도구 / 옵션** 대화 상자, 속성 창 및 다른 특정 대화 상자. Visual Studio 확장명 적은 양의 데이터를 저장 하려면이 사용할 수 있습니다. 이 연습에서는 읽기 및 사용자 설정 저장소에 기록 하 여 Visual Studio에는 외부 도구도 메모장을 추가 하는 방법을 보여 줍니다.  
  
### <a name="backing-up-your-user-settings"></a>Your 사용자 설정 백업  
  
1.  디버깅 하 고이 절차를 반복 수 있도록 외부 도구 설정을 다시 설정 수 있어야 합니다. 이 작업을 수행 하려면 필요에 따라 복원할 수 있도록 원래 설정을 저장 해야 합니다.  
  
2.  Regedit.exe를 엽니다.  
  
3.  HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\14.0Exp\External Tools로 이동\\합니다.  
  
    > [!NOTE]
    >  \14.0Exp\ 및 하지 \14.0을 포함 하는 키에 찾고 확인\\합니다. Visual Studio의 실험적 인스턴스를 실행 하는 경우 레지스트리 하이브 "14.0Exp"에 사용자 설정 됩니다.  
  
4.  \External Tools\ 하위 키를 마우스 오른쪽 단추로 누른 **내보내기**합니다. 다음 사항을 확인 **선택한 분기** 을 선택 합니다.  
  
5.  생성 되는 외부 Tools.reg 파일을 저장 합니다.  
  
6.  외부 도구 설정을 다시 설정 하려는 경우 HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\14.0Exp\External Tools\ 레지스트리 키를 선택 하 고 클릭 나중 **삭제** 상황에 맞는 메뉴입니다.  
  
7.  경우는 **키 삭제 확인** 대화 상자가 나타나면 클릭 **예**합니다.  
  
8.  이전에 저장 하는 외부 Tools.reg 파일을 마우스 오른쪽 단추로 클릭 하 여, **로 열기**, 클릭 하 고 **레지스트리 편집기**합니다.  
  
## <a name="writing-to-the-user-settings-store"></a>사용자 설정 저장소에 쓰기  
  
1.  UserSettingsStoreExtension 라는 VSIX 프로젝트 만들고 UserSettingsStoreCommand 라는 사용자 지정 명령 추가 합니다. 사용자 지정 명령을 만드는 방법에 대 한 자세한 내용은 참조 [메뉴 명령을 사용 하 여 확장 만들기](../extensibility/creating-an-extension-with-a-menu-command.md)  
  
2.  UserSettingsStoreCommand.cs에 다음 추가 문을 사용 하 여:  
  
    ```csharp  
    using System.Collections.Generic;  
    using Microsoft.VisualStudio.Settings;  
    using Microsoft.VisualStudio.Shell.Settings;  
    ```  
  
3.  MenuItemCallback에서 메서드의 본문을 삭제 하 고 다음과 같이 설정 저장 사용자 가져오기:  
  
    ```csharp  
    private void MenuItemCallback(object sender, EventArgs e)  
    {  
        SettingsManager settingsManager = new ShellSettingsManager(ServiceProvider);  
        WritableSettingsStore userSettingsStore = settingsManager.GetWritableSettingsStore(SettingsScope.UserSettings);  
    }  
    ```  
  
4.  이제 메모장 외부 도구로 이미 설정 되어 있는지 알아보십시오. 되는지 확인 하려면 ToolCmd 설정은 "Notepad" 다음과 같은 모든 외부 도구를 반복 해야 합니다.  
  
    ```csharp  
    private void MenuItemCallback(object sender, EventArgs e)  
    {  
        SettingsManager settingsManager = new ShellSettingsManager(ServiceProvider);  
        WritableSettingsStore userSettingsStore = settingsManager.GetWritableSettingsStore(SettingsScope.UserSettings);  
  
        // Find out whether Notepad is already an External Tool.  
        int toolCount = userSettingsStore.GetInt32("External Tools", "ToolNumKeys");  
        bool hasNotepad = false;  
        CompareInfo Compare = CultureInfo.InvariantCulture.CompareInfo;  
        for (int i = 0; i < toolCount; i++)  
        {  
            if (Compare.IndexOf(userSettingsStore.GetString("External Tools", "ToolCmd" + i), "Notepad", CompareOptions.IgnoreCase) >= 0)  
            {  
                hasNotepad = true;  
                break;  
            }  
        }  
    }  
  
    ```  
  
5.  메모장 외부 도구로 설정 되지 않은 경우이 다음과 같이 설정.  
  
    ```vb  
    private void MenuItemCallback(object sender, EventArgs e)  
    {  
        SettingsManager settingsManager = new ShellSettingsManager(ServiceProvider);  
        WritableSettingsStore userSettingsStore = settingsManager.GetWritableSettingsStore(SettingsScope.UserSettings);  
  
        // Find out whether Notepad is already installed.  
        int toolCount = userSettingsStore.GetInt32("External Tools", "ToolNumKeys");  
        bool hasNotepad = false;  
        CompareInfo Compare = CultureInfo.InvariantCulture.CompareInfo;  
        for (int i = 0; i < toolCount; i++)  
        {  
            if (Compare.IndexOf(userSettingsStore.GetString("External Tools", "ToolCmd" + i), "Notepad", CompareOptions.IgnoreCase) >= 0)  
            {  
                hasNotepad = true;  
                break;  
            }  
        }  
  
        string message = (hasNotepad) ? "Notepad already installed" : "Installing Notepad";  
         if (!hasNotepad)  
        {  
            userSettingsStore.SetString("External Tools", "ToolTitle" + toolCount, "&Notepad");  
            userSettingsStore.SetString("External Tools", "ToolCmd" + toolCount, "C:\\Windows\\notepad.exe");  
            userSettingsStore.SetString("External Tools", "ToolArg" + toolCount, "");  
            userSettingsStore.SetString("External Tools", "ToolDir" + toolCount, "$(ProjectDir)");  
            userSettingsStore.SetString("External Tools", "ToolSourceKey" + toolCount, "");  
            userSettingsStore.SetUInt32("External Tools", "ToolOpt" + toolCount, 0x00000011);  
  
            userSettingsStore.SetInt32("External Tools", "ToolNumKeys", toolCount + 1);  
        }  
    }  
    ```  
  
6.  코드를 테스트 합니다. 추가 메모장 외부 도구로 롤백해야 레지스트리를 두 번째로 실행 하기 전에 실행 해야 합니다.  
  
7.  코드를 빌드하고 디버깅을 시작 합니다.  
  
8.  에 **도구** 메뉴를 클릭 하 여 **UserSettingsStoreCommand 호출**합니다. 메모장을 추가 합니다.는 **도구** 메뉴.  
  
9. 메모장 도구에 표시 되어야 하는 이제 / 옵션 메뉴를 클릭 한 **메모장** 메모장의 인스턴스를 준비 해야 합니다.