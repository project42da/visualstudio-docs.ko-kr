---
title: "VSTO 추가 기능에 대한 레지스트리 항목 | Microsoft Docs"
ms.custom: ""
ms.date: "02/02/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "office-development"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "LoadBehavior 항목"
  - "추가 기능[Visual Studio에서 Office 개발], 레지스트리 항목"
  - "레지스트리 키[Visual Studio에서 Office 개발]"
  - "응용 프로그램 수준 추가 기능[Visual Studio에서 Office 개발], 레지스트리 항목"
  - "레지스트리 항목[Visual Studio에서 Office 개발]"
ms.assetid: 319e5bbc-0234-4af0-91ce-54bcfafc173f
caps.latest.revision: 79
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 78
---
# VSTO 추가 기능에 대한 레지스트리 항목
  Visual Studio를 사용하여 만든 VSTO 추가 기능을 배포할 때에는 특정 레지스트리 항목 집합을 만들어야 합니다. 이러한 레지스트리 항목은 Microsoft Office 응용 프로그램에서 VSTO 추가 기능을 찾아 로드할 수 있는 정보를 제공합니다.  
  
 [!INCLUDE[appliesto_allapp](../vsto/includes/appliesto-allapp-md.md)]  
  
 프로젝트를 빌드할 때 Visual Studio에서는 VSTO 추가 기능을 쉽게 실행하고 디버그할 수 있도록 개발 컴퓨터에서 이들 레지스트리 항목을 만듭니다. ClickOnce를 사용하여 VSTO 추가 기능을 배포하는 경우 레지스트리 항목이 자동으로 최종 사용자 컴퓨터에 생성됩니다. Windows Installer를 사용하여 VSTO 추가 기능을 배포하는 경우 InstallShield Limited Edition 프로젝트를 구성하여 최종 사용자 컴퓨터에 레지스트리 항목을 만들어야 합니다.  
  
 VSTO 추가 기능에 대한 로드 프로세스 중 레지스트리 항목을 사용하는 방법에 대한 자세한 내용은 [VSTO 추가 기능의 아키텍처](../vsto/architecture-of-vsto-add-ins.md)를 참조하세요.  
  
> [!NOTE]  
>  이 항목에서 *추가 기능 ID* 텍스트는 VSTO 추가 기능의 고유한 ID를 나타냅니다. 기본적으로 ID는 VSTO 추가 기능 어셈블리의 이름입니다.  
  
## 현재 사용자 및 모든 사용자의 VSTO 추가 기능 등록  
 VSTO 추가 기능을 설치할 때 두 가지 방법으로 등록할 수 있습니다.  
  
-   현재 사용자 전용\(즉, VSTO 추가 기능을 설치할 때 컴퓨터에 로그온한 사용자만 사용 가능\). 이 경우 레지스트리 항목은 HKEY\_CURRENT\_USER에 생성됩니다.  
  
-   모든 사용자용\(즉, 컴퓨터에 로그온한 사용자는 모두 VSTO 추가 기능 사용 가능\). 이 경우 레지스트리 항목은 HKEY\_LOCAL\_MACHINE에 생성됩니다.  
  
 Visual Studio를 사용하여 만드는 모든 VSTO 추가 기능은 현재 사용자용으로 등록할 수 있습니다. 그러나 특정 시나리오에서는 VSTO 추가 기능을 모든 사용자용으로만 등록할 수 있습니다. 이러한 시나리오는 컴퓨터의 Microsoft Office 버전과 VSTO 추가 기능이 배포된 방법에 따라 다릅니다.  
  
### Microsoft Office 버전  
 Office 응용 프로그램은 HKEY\_LOCAL\_MACHINE 또는 HKEY\_CURRENT\_USER에 등록된 VSTO 추가 기능을 로드할 수 있습니다.  
  
 HKEY\_LOCAL\_MACHINE에 등록된 VSTO 추가 기능을 로드하려면 컴퓨터에 업데이트 패키지 976477이 설치되어 있어야 합니다. 자세한 내용은 [http:\/\/go.microsoft.com\/fwlink\/?LinkId\=184923](http://go.microsoft.com/fwlink/?LinkId=184923)를 참조하세요.  
  
### 배포 형식  
 ClickOnce를 사용하여 VSTO 추가 기능을 배포하는 경우 VSTO 추가 기능을 현재 사용자 전용으로 등록할 수 있습니다. ClickOnce가 HKEY\_CURRENT\_USER에 키 생성만 지원하기 때문입니다. 컴퓨터의 모든 사용자에 대해 VSTO 추가 기능을 등록하려면 Windows Installer를 사용하여 VSTO 추가 기능을 배포해야 합니다. 이러한 배포 형식에 대한 자세한 내용은 [ClickOnce를 사용하여 Office 솔루션 배포](../vsto/deploying-an-office-solution-by-using-clickonce.md) 및 [Windows Installer를 사용하여 Office 솔루션 배포](../vsto/deploying-an-office-solution-by-using-windows-installer.md)를 참조하세요.  
  
## 레지스트리 항목  
 필요한 VSTO 추가 기능 레지스트리 항목은 Visio를 제외한 모든 응용 프로그램에 대해 다음 레지스트리 키 아래에 있습니다. 여기에서 *루트*는 HKEY\_CURRENT\_USER 또는 HKEY\_LOCAL\_MACHINE입니다.  
  
 **Visio를 제외한 모든 응용 프로그램**  
  
|Office 버전|구성 경로|  
|---------------|-----------|  
|32비트|*Root*\\Software\\Microsoft\\Office\\*application name*\\Addins\\*add\-in ID*|  
|64비트|*Root*\\Software\\Wow6432Node\\Microsoft\\Office\\*application name*\\Addins\\*add\-in ID*|  
  
 **Visio**  
  
|Office 버전|구성 경로|  
|---------------|-----------|  
|32비트|*Root*\\Software\\Microsoft\\Visio\\Addins\\*add\-in ID*|  
|64비트|*Root*\\Software\\Wow6432Node\\Visio\\Addins\\*add\-in ID*|  
  
 다음 테이블에는 이 레지스트리 키의 항목이 나열되어 있습니다.  
  
|입력|형식|값|  
|--------|--------|-------|  
|**Description**|REG\_SZ|필수 요소. VSTO 추가 기능에 대한 간략한 설명입니다.<br /><br /> 이 설명은 사용자가 Microsoft Office 응용 프로그램의 **옵션** 대화 상자에 있는 **추가 기능** 창의 VSTO 추가 기능을 선택했을 때 표시됩니다.|  
|**FriendlyName**|REG\_SZ|필수 요소. Microsoft Office 응용 프로그램의 **COM 추가 기능** 대화 상자에 표시되는 VSTO 추가 기능에 대한 설명이 포함된 이름입니다. 기본값은 VSTO 추가 기능 ID입니다.|  
|**LoadBehavior**|REG\_DWORD|필수 요소. 응용 프로그램에서 VSTO 추가 기능 및 VSTO 추가 기능의 현재 상태\(로드 또는 언로드\)를 로드하려고 할 때 지정하는 값입니다.<br /><br /> 기본적으로 이 항목은 시작 시 VSTO 추가 기능을 로드하도록 지정하는 3으로 설정됩니다. 자세한 내용은 [LoadBehavior 값](#LoadBehavior)을 참조하세요. **Note:**  사용자가 VSTO 추가 기능을 사용하지 않도록 설정하는 경우 HKEY\_CURRENT\_USER 레지스트리 하이브의 **LoadBehavior** 값이 수정됩니다. 각 사용자에 대해 HKEY\_CURRENT\_USER 하이브의 **LoadBehavior** 값이 HKEY\_LOCAL\_MACHINE 하이브에 정의된 기본값 **LoadBehavior**를 재정의합니다.|  
|**Manifest**|REG\_SZ|필수 요소. VSTO 추가 기능에 대한 배포 매니페스트의 전체 경로입니다. 경로는 로컬 컴퓨터, 네트워크 공유\(UNC\) 또는 웹 서버\(HTTP\)의 위치일 수 있습니다.<br /><br /> Windows Installer를 사용하여 솔루션을 배포하는 경우 **매니페스트** 경로에 접두사 **file:\/\/\/**을 추가해야 합니다. 또한 문자열 **&#124;vstolocal**\(즉, 파이프 문자 **&#124;** 뒤에 **vstolocal**이 나옴\)을 이 경로 끝에 추가해야 합니다. 그러면 솔루션이 ClickOnce 캐시가 아니라 설치 폴더에서 로드됩니다. 자세한 내용은 [Windows Installer를 사용하여 Office 솔루션 배포](../vsto/deploying-an-office-solution-by-using-windows-installer.md)을 참조하십시오. **Note:**  개발 컴퓨터에서 VSTO 추가 기능을 빌드할 때 Visual Studio에서 자동으로 **&#124;vstolocal** 문자열을 이 레지스트리 항목에 추가합니다.|  
  
###  <a name="OutlookEntries"></a> Outlook 양식 영역에 대한 레지스트리 항목  
 Outlook용 VSTO 추가 기능에 사용자 지정 양식 영역을 만들 경우 추가 레지스트리 항목을 사용하여 Outlook에 양식 영역을 등록합니다. 이러한 항목은 양식 영역을 지원하는 각 메시지 클래스에 대한 다른 레지스트리 키 아래에 만들어집니다. 이 레지스트리 키는 다음 위치에 있습니다. 여기에서 *루트*는 HKEY\_CURRENT\_USER 또는 HKEY\_LOCAL\_MACHINE입니다.  
  
 *루트*\\Software\\Microsoft\\Office\\Outlook\\FormRegions\\*message class*  
  
 모든 VSTO 추가 기능에서 다른 레지스트리 항목을 공유하는 것처럼, 프로젝트를 빌드할 때 Visual Studio는 개발 컴퓨터에 양식 영역 레지스트리 항목을 만듭니다. ClickOnce를 사용하여 VSTO 추가 기능을 배포하는 경우 레지스트리 항목이 자동으로 최종 사용자 컴퓨터에 생성됩니다. Windows Installer를 사용하여 VSTO 추가 기능을 배포하는 경우 InstallShield Limited Edition 프로젝트를 구성하여 최종 사용자 컴퓨터에 레지스트리 항목을 만들어야 합니다.  
  
 양식 영역 레지스트리 항목에 대한 자세한 내용은 [Windows 레지스트리에 양식 영역 지정](HV10038637)을 참조하세요. Outlook 양식 영역에 대한 자세한 내용은 [Outlook 양식 영역 만들기](../vsto/creating-outlook-form-regions.md)를 참조하세요.  
  
##  <a name="LoadBehavior"></a> LoadBehavior 값  
 *루트*\\Software\\Microsoft\\Office\\*application name*\\Addins\\*add\-in ID* 키 아래의 **LoadBehavior** 항목에는 VSTO 추가 기능의 런타임 동작을 지정하는 비트 조합 값이 들어 있습니다. 가장 낮은 순서 비트\(값 0과 1\)는 VSTO 추가 기능이 현재 로드되었는지 여부를 나타냅니다. 다른 비트는 응용 프로그램에서 VSTO 추가 기능을 로드하는 시기를 나타냅니다.  
  
 최종 사용자 컴퓨터에 VSTO 추가 기능이 설치될 때, 일반적으로 **LoadBehavior** 항목은 0, 3 또는 16\(10진수\)으로 설정됩니다. VSTO 추가 기능을 빌드하거나 게시할 때, 기본적으로 Visual Studio는 VSTO 추가 기능의 **LoadBehavior** 항목을 3으로 설정합니다.  
  
 다음 표에서는 **LoadBehavior** 항목의 가능한 모든 값을 모두 보여 줍니다. 이 표의 일부 설명은 VSTO 추가 기능 수동으로 또는 프로그래밍 방식으로 로드를 참조합니다. VSTO 추가 기능을 수동으로 로드하려면 응용 프로그램의 **COM 추가 기능** 대화 상자에서 VSTO 추가 기능 옆에 있는 확인란을 선택합니다. VSTO 추가 기능을 프로그래밍 방식으로 로드하려면 **true**에 대한 VSTO 추가 기능을 나타내는 <xref:Microsoft.Office.Core.COMAddIn> 개체의 <xref:Microsoft.Office.Core.COMAddIn.Connect%2A> 속성을 설정합니다.  
  
|값\(10 진수\)|VSTO 추가 기능 상태|VSTO 추가 기능 로드 동작|설명|  
|----------------|-------------------|----------------------|--------|  
|0|언로드됨|자동으로 로드하지 않음|응용 프로그램이 VSTO 추가 기능을 자동으로 로드하지 않습니다. 사용자는 VSTO 추가 기능을 수동으로 로드하거나, VSTO 추가 기능을 프로그래밍 방식으로 로드할 수 있습니다.<br /><br /> VSTO 추가 기능이 성공적으로 로드되면 **LoadBehavior** 값은 0으로 유지되지만 **COM 추가 기능** 대화 상자의 VSTO 추가 기능 상태는 업데이트되어 VSTO 추가 기능이 로드된 것으로 나타납니다.|  
|1|로드됨|자동으로 로드하지 않음|응용 프로그램이 VSTO 추가 기능을 자동으로 로드하지 않습니다. 사용자는 VSTO 추가 기능을 수동으로 로드하거나, VSTO 추가 기능을 프로그래밍 방식으로 로드할 수 있습니다.<br /><br /> **COM 추가 기능** 대화 상자에 응용 프로그램이 시작된 후 VSTO 추가 기능이 로드된 것으로 나타나지만, VSTO 추가 기능은 수동으로 또는 프로그래밍 방식으로 로드될 때까지 실제로 로드되지 않습니다.<br /><br /> 응용 프로그램에서 VSTO 추가 기능을 성공적으로 로드하면 **LoadBehavior** 값이 0으로 바뀌며, 응용 프로그램을 종료하면 0으로 유지됩니다.|  
|2|언로드됨|시작 시 로드|응용 프로그램이 VSTO 추가 기능을 자동으로 로드하지 않습니다. 사용자는 VSTO 추가 기능을 수동으로 로드하거나, VSTO 추가 기능을 프로그래밍 방식으로 로드할 수 있습니다.<br /><br /> 응용 프로그램에서 VSTO 추가 기능을 성공적으로 로드하면 **LoadBehavior** 값이 3으로 바뀌며, 응용 프로그램을 종료하면 3으로 유지됩니다.|  
|3|로드됨|시작 시 로드|응용 프로그램을 시작하면 응용 프로그램에서 VSTO 추가 기능을 로드합니다. Visual Studio에서 VSTO 추가 기능을 빌드하거나 게시할 때 기본값입니다.<br /><br /> 응용 프로그램이 VSTO 추가 기능을 성공적으로 로드하면 **LoadBehavior** 값이 3으로 유지됩니다. VSTO 추가 기능을 로드할 때 오류가 발생하면 **LoadBehavior** 값이 2로 바뀌며, 응용 프로그램을 종료하면 2로 유지됩니다.|  
|8|언로드됨|요청 시 로드|응용 프로그램이 VSTO 추가 기능을 자동으로 로드하지 않습니다. 사용자는 VSTO 추가 기능을 수동으로 로드하거나, VSTO 추가 기능을 프로그래밍 방식으로 로드할 수 있습니다.<br /><br /> 응용 프로그램이 VSTO 추가 기능을 성공적으로 로드하면 **LoadBehavior** 값이 9로 바뀝니다.|  
|10|로드됨|요청 시 로드|사용자가 VSTO 추가 기능의 기능을 사용하는 UI 요소를 클릭할 때처럼\(예: 리본의 사용자 지정 단추\), VSTO 추가 기능은 응용 프로그램에서 필요로 하는 경우에만 로드됩니다.<br /><br /> 응용 프로그램에서 VSTO 추가 기능을 성공적으로 로드하면 **LoadBehavior** 값은 9로 유지되지만 **COM 추가 기능** 대화 상자의 VSTO 추가 기능 상태는 업데이트되어 VSTO 추가 기능이 현재 로드된 것으로 나타납니다. VSTO 추가 기능을 로드할 때 오류가 발생하는 경우는 **LoadBehavior** 값이 8로 바뀝니다.|  
|16|로드됨|처음으로 로드한 다음 요청 시 로드|VSTO 추가 기능이 요청 시 로드되도록 하려면 이 값을 설정합니다. 사용자가 응용 프로그램을 처음으로 실행할 때 응용 프로그램에서 VSTO 추가 기능을 로드합니다. 사용자가 다음에 응용 프로그램을 실행하면 응용 프로그램에서 VSTO 추가 기능에서 정의한 UI 요소를 로드합니다. 그러나 사용자가 VSTO 추가 기능과 연결된 UI 요소를 클릭할 때까지 VSTO 추가 기능은 로드되지 않습니다.<br /><br /> 응용 프로그램에서 처음으로 VSTO 추가 기능을 로드할 때 VSTO 추가 기능이 로드되는 동안 **LoadBehavior** 값은 16으로 유지됩니다. 응용 프로그램을 닫은 후에는 **LoadBehavior** 값이 9로 바뀝니다.|  
  
## 참고 항목  
 [Visual Studio의 Office 솔루션 아키텍처](../vsto/architecture-of-office-solutions-in-visual-studio.md)   
 [VSTO 추가 기능의 아키텍처](../vsto/architecture-of-vsto-add-ins.md)   
 [Office 솔루션 빌드](../vsto/building-office-solutions.md)   
 [Office 솔루션 배포](../vsto/deploying-an-office-solution.md)  
  
  