---
title: "설정 저장소에서 서비스 정보 가져오기 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 7028d440-d16d-4b08-9b94-eb8cc93b25fc
caps.latest.revision: 4
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 4
---
# 설정 저장소에서 서비스 정보 가져오기
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

모든 사용 가능한 서비스를 찾으려면 또는 특정 서비스가 설치 되어 있는지 확인 하려면 설정 저장소를 사용할 수 있습니다. 서비스 클래스의 형식을 알고 있어야 합니다.  
  
### 사용 가능한 서비스를 나열 하려면  
  
1.  FindServicesExtension 라는 VSIX 프로젝트를 하 고 FindServicesCommand 라는 사용자 지정 명령을 추가 합니다. 사용자 지정 명령을 만드는 방법에 대 한 자세한 내용은 참조 하십시오. [메뉴 명령을 사용 하 여 확장 만들기](../extensibility/creating-an-extension-with-a-menu-command.md)  
  
2.  FindServicesCommand.cs에서 다음 추가 문을 사용 하 여:  
  
    ```vb  
    using System.Collections.Generic; using Microsoft.VisualStudio.Settings; using Microsoft.VisualStudio.Shell.Settings; using System.Windows.Forms;  
    ```  
  
3.  구성 설정 저장소를 가져와 다음 서비스 라는 하위 컬렉션을 찾습니다. 이 컬렉션에 사용 가능한 모든 서비스가 포함 되어 있습니다. MenuItemCommand 메서드에서 기존 코드를 제거 하 고 다음으로 바꿉니다.  
  
    ```  
    private void MenuItemCallback(object sender, EventArgs e) { SettingsManager settingsManager = new ShellSettingsManager(ServiceProvider); SettingsStore configurationSettingsStore = settingsManager.GetReadOnlySettingsStore(SettingsScope.Configuration); string message = "Available services:\n"; IEnumerable<string> collection = configurationSettingsStore.GetSubCollectionNames("Services"); int n = 0; foreach (string service in collection) { message += configurationSettingsStore.GetString("Services\\" + service, "Name", "Unknown") + "\n"; } MessageBox.Show(message); }  
    ```  
  
4.  프로젝트를 빌드하고 디버깅을 시작합니다. 실험적 인스턴스가 표시 됩니다.  
  
5.  실험적 인스턴스에서는 **도구** 메뉴를 클릭 하 여 **FindServicesCommand 호출**합니다.  
  
     모든 서비스를 나열 하는 메시지 상자가 표시 됩니다.  
  
     이러한 설정은 확인 하려면 레지스트리 편집기를 사용할 수 있습니다.  
  
## 특정 서비스를 찾고  
 사용할 수도 있습니다는 <xref:Microsoft.VisualStudio.Settings.SettingsStore.CollectionExists%2A> 메서드를 특정 서비스 설치 되어 있는지 확인 합니다. 서비스 클래스의 형식을 알고 있어야 합니다.  
  
1.  이전 절차에서 만든 프로젝트의 MenuItemCallback, 검색에 대 한 구성 설정 저장소는 `Services` 서비스의 GUID로 명명 된 하위 들어 있는 컬렉션입니다. 이 경우 도움말 서비스에 대해 살펴보겠습니다.  
  
    ```  
    private void MenuItemCallback(object sender, EventArgs e) { SettingsManager settingsManager = new ShellSettingsManager(ServiceProvider); SettingsStore configurationSettingsStore = settingsManager.GetReadOnlySettingsStore(SettingsScope.Configuration); string helpServiceGUID = typeof(SVsHelpService).GUID.ToString("B").ToUpper(); bool hasHelpService = configurationSettingsStore.CollectionExists("Services\\" + helpServiceGUID); string message = "Help Service Available: " + hasHelpService; MessageBox.Show(message); }  
    ```  
  
2.  프로젝트를 빌드하고 디버깅을 시작합니다.  
  
3.  실험적 인스턴스에서는 **도구** 메뉴를 클릭 하 여 **FindServicesCommand 호출**합니다.  
  
     텍스트가 포함 된 메시지를 확인 해야 **서비스를 사용할 수 하는 데 도움이:**  뒤 **True** 또는 **False**합니다. 이 설정은 확인 하려면 이전 단계에서 표시 된 것 처럼 레지스트리 편집기를 사용할 수 있습니다.