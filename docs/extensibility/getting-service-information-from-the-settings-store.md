---
title: "설정 저장소에서 서비스 정보 가져오기 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7028d440-d16d-4b08-9b94-eb8cc93b25fc
caps.latest.revision: "4"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: a8508f0d017ba94981f5f54c7a8b63c7528ac6e9
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="getting-service-information-from-the-settings-store"></a>설정 저장소에서 서비스 정보 가져오기
모든 사용 가능한 서비스를 확인 하거나 특정 서비스가 설치 되어 있는지 여부를 확인 하려면 설정 저장소를 사용할 수 있습니다. 서비스 클래스의 형식을 알고 있어야 합니다.  
  
### <a name="to-list-the-available-services"></a>사용 가능한 서비스를 나열 하려면  
  
1.  FindServicesExtension 라는 VSIX 프로젝트 만들고 FindServicesCommand 라는 사용자 지정 명령 추가 합니다. 사용자 지정 명령을 만드는 방법에 대 한 자세한 내용은 참조 [메뉴 명령을 사용 하 여 확장 만들기](../extensibility/creating-an-extension-with-a-menu-command.md)  
  
2.  FindServicesCommand.cs에 다음 추가 문을 사용 하 여:  
  
    ```vb  
    using System.Collections.Generic;  
    using Microsoft.VisualStudio.Settings;  
    using Microsoft.VisualStudio.Shell.Settings;  
    using System.Windows.Forms;  
    ```  
  
3.  명명 된 서비스 하위를 찾은 다음 구성 설정 저장소를 가져옵니다. 이 컬렉션에 사용 가능한 서비스를 모두 포함 됩니다. MenuItemCommand 메서드를 기존 코드를 제거 하 고 다음으로 바꿉니다.  
  
    ```  
    private void MenuItemCallback(object sender, EventArgs e)  
    {  
        SettingsManager settingsManager = new ShellSettingsManager(ServiceProvider);  
        SettingsStore configurationSettingsStore = settingsManager.GetReadOnlySettingsStore(SettingsScope.Configuration);  
        string message = "Available services:\n";  
        IEnumerable<string> collection = configurationSettingsStore.GetSubCollectionNames("Services");  
        int n = 0;  
        foreach (string service in collection)  
        {  
            message += configurationSettingsStore.GetString("Services\\" + service, "Name", "Unknown") + "\n";  
        }  
  
        MessageBox.Show(message);  
    }  
    ```  
  
4.  프로젝트를 빌드하고 디버깅을 시작합니다. 실험적 인스턴스가 표시 됩니다.  
  
5.  실험적 인스턴스에서는 **도구** 메뉴를 클릭 하 여 **호출 FindServicesCommand**합니다.  
  
     모든 서비스를 나열 하는 메시지 상자가 나타납니다.  
  
     이러한 설정을 확인 하려면 레지스트리 편집기를 사용할 수 있습니다.  
  
## <a name="finding-a-specific-service"></a>특정 서비스를 찾고  
 사용할 수도 있습니다는 <xref:Microsoft.VisualStudio.Settings.SettingsStore.CollectionExists%2A> 메서드를 특정 서비스가 설치 되어 있는지 여부를 확인 합니다. 서비스 클래스의 형식을 알고 있어야 합니다.  
  
1.  이전 절차에서 만든 프로젝트의 MenuItemCallback, 검색에 대 한 구성 설정 저장소는 `Services` 서비스의 GUID에 의해 명명 된 하위 들어 있는 컬렉션입니다. 이 예에서 도움말 서비스에 대해 살펴보겠습니다.  
  
    ```  
    private void MenuItemCallback(object sender, EventArgs e)  
    {  
        SettingsManager settingsManager = new ShellSettingsManager(ServiceProvider);  
        SettingsStore configurationSettingsStore = settingsManager.GetReadOnlySettingsStore(SettingsScope.Configuration);  
        string helpServiceGUID = typeof(SVsHelpService).GUID.ToString("B").ToUpper();  
        bool hasHelpService = configurationSettingsStore.CollectionExists("Services\\" + helpServiceGUID);  
        string message = "Help Service Available: " + hasHelpService;  
  
        MessageBox.Show(message);  
    }  
    ```  
  
2.  프로젝트를 빌드하고 디버깅을 시작합니다.  
  
3.  실험적 인스턴스에서는 **도구** 메뉴를 클릭 하 여 **호출 FindServicesCommand**합니다.  
  
     메시지 텍스트와 함께 표시 되어야 **서비스를 사용할 수 하는 데 도움이:** 이어서 **True** 또는 **False**합니다. 이 설정은 확인 하려면 이전 단계에서와 같이 레지스트리 편집기를 사용할 수 있습니다.