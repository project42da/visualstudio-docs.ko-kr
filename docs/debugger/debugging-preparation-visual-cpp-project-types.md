---
title: '디버깅 준비: Visual c + + 프로젝트 형식을 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- project templates, debugging
- Visual C++ projects, debugging
- debug builds, project settings
- debugging [C++]
ms.assetid: 912b4ba2-7719-43d5-b087-db33e3f9329a
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- cplusplus
ms.openlocfilehash: e02be24447d5383388be0a7208bf84e36333732f
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="debugging-preparation-visual-c-project-types"></a>디버깅 준비: Visual C++ 프로젝트 형식
이 단원에서는 [!INCLUDE[vcprvc](../code-quality/includes/vcprvc_md.md)] 프로젝트 템플릿으로 만든 기본 프로젝트 형식을 디버깅하는 방법에 대해 설명합니다.  
  
 참고로 그룹화 된 출력으로 Dll을 생성 하는 이러한 프로젝트 형식을 [DLL 프로젝트 디버깅](../debugger/debugging-dll-projects.md) 는 공통적인 특징 때문입니다.  
  
##  <a name="BKMK_In_this_topic"></a> 항목 내용  
 [권장된 속성 설정](#BKMK_Recommended_Property_Settings)  
  
 [Win32 프로젝트](#BKMK_Win32_Projects)  
  
-   [C 또는 c + + Win32 응용 프로그램의 디버깅](#BKMK_To_debug_a_C_or_C___Win32_application)  
  
-   [디버그 구성을 직접 설정 하려면](#BKMK_To_manually_set_a_Debug_configuration)  
  
 [Windows Forms 응용 프로그램 (.NET)](#BKMK_Windows_Forms_Applications___NET_)  
  
##  <a name="BKMK_Recommended_Property_Settings"></a> 권장된 속성 설정  
 일부 속성은 모든 관리되지 않는 디버깅 시나리오에서 동일한 방식으로 설정해야 합니다. 다음 표에는 권장 속성 설정이 나와 있습니다. 여기에 나와 있지 않은 설정은 관리되지 않는 프로젝트 형식에 따라 서로 다를 수 있습니다. 자세한 내용은 참조 [c + + 디버그 구성에 대 한 프로젝트 설정](../debugger/project-settings-for-a-cpp-debug-configuration.md)  
  
### <a name="configuration-properties-124-cc-124-optimization-node"></a>구성 속성 &#124; C/c + + &#124; 최적화 노드  
  
|속성 이름|설정|  
|-------------------|-------------|  
|**Optimization**|로 설정 **사용 안 함 (/ 0d).** 코드를 최적화하면, 생성되는 명령이 소스 코드에 직접 대응되지 않기 때문에 디버깅하기 어렵습니다. 에이 설정을 선택할 수 있지만에 표시 되는 코드 최적화 된 코드에만 나타나는 버그가 프로그램에서 발견 하는 경우는 **디스어셈블리** 창 소스에 나타나는 일치 하지 않는 최적화 된 소스에서 생성 됩니다 창입니다. 단계별 실행과 같은 다른 기능이 정상적으로 작동하지 않을 수도 있습니다.|  
  
### <a name="configuration-properties-124-linker-124-debugging-node"></a>구성 속성 &#124; 링커 &#124; 디버깅 노드  
  
|속성 이름|설정|  
|-------------------|-------------|  
|**디버깅 정보 생성**|항상이 옵션을 설정 해야 **예 (/debug)** 디버깅 기호와 디버깅에 필요한 파일을 만들려고 합니다. 응용 프로그램을 제품화할 때는 이 옵션을 해제할 수 있습니다.|  
  
 [항목 내용](../debugger/debugging-preparation-visual-cpp-project-types.md#BKMK_In_this_topic)  
  
##  <a name="BKMK_Win32_Projects"></a> Win32 프로젝트  
 Win32 응용 프로그램은 C 또는 C++로 작성된 일반 Windows 프로그램입니다. 이러한 형식의 응용 프로그램은 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에서 쉽게 디버깅할 수 있습니다.  
  
 Win32 응용 프로그램에는 MFC 응용 프로그램과 ATL 프로젝트가 포함됩니다. Win32 응용 프로그램은 Windows API를 사용하며 MFC나 ATL을 사용할 수도 있지만 CLR(공용 언어 런타임)는 사용하지 않습니다. 그러나 CLR을 사용하는 관리 코드를 호출할 수는 있습니다.  
  
 다음은 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 내에서 Win32 프로젝트를 디버깅하는 방법을 보여 주는 절차입니다. [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 외부에서 응용 프로그램을 시작하고 여기에 연결하는 방법으로 Win32 응용 프로그램을 디버깅할 수도 있습니다. 자세한 내용은 참조 [실행 중인 프로세스에 연결할](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md)합니다.  
  
###  <a name="BKMK_To_debug_a_C_or_C___Win32_application"></a> C 또는 c + + Win32 응용 프로그램의 디버깅  
  
1.  Visual Studio에서 프로젝트를 엽니다.  
  
2.  에 **디버그** 메뉴 선택 **시작**합니다.  
  
3.  에 설명 된 기술을 사용 하 여 디버깅 [디버거 기본 사항](../debugger/debugger-basics.md)합니다.  
  
###  <a name="BKMK_To_manually_set_a_Debug_configuration"></a> 디버그 구성을 직접 설정 하려면  
  
1.  에 **보기** 메뉴를 클릭 하 여 **속성 페이지**합니다.  
  
2.  클릭는 **구성 속성** 노드가 아직 없는 경우  
  
3.  선택 **일반**의 값을 설정 하 고는 **출력** 행 **디버그**합니다.  
  
4.  열기는 **C/c + +** 노드를 선택한 **일반**합니다.  
  
     에 **디버그** 행 디버깅 컴파일러에 의해 생성 되는 정보 유형을 지정 합니다. 값으로 선택할 수 있습니다 **프로그램 데이터베이스 (/Zi)** 또는 **편집 하며 계속 하기 (/ZI)에 대 한 프로그램 데이터베이스**합니다.  
  
5.  선택 **최적화**, 및는 **최적화** 행, **사용 안 함 (/ 0d)** 드롭 다운 목록에서 합니다.  
  
     코드를 최적화하면, 생성되는 명령이 소스 코드에 직접 대응되지 않기 때문에 디버깅하기 어렵습니다. 최적화된 코드에만 나타나는 버그가 프로그램에서 발견될 경우에는 이 설정을 선택할 수 있습니다. 그러나 디스어셈블리 창에 표시되는 코드는 소스 창에 표시되는 코드와 일치하지 않는 최적화된 코드에서 생성되므로, 단계별 실행 같은 기능을 수행하면 중단점과 실행 지점이 올바르게 표시되지 않을 수 있습니다.  
  
6.  열기는 **링커** 노드를 선택한 **디버깅**합니다. 첫 번째 범위에서 **생성** 행, **예 (/debug)** 드롭 다운 목록에서 합니다. 디버깅하는 경우 항상 이 값으로 설정해야 합니다.  
  
 자세한 내용은 참조[c + + 디버그 구성에 대 한 프로젝트 설정을](../debugger/project-settings-for-a-cpp-debug-configuration.md)합니다.  
  
 [항목 내용](../debugger/debugging-preparation-visual-cpp-project-types.md#BKMK_In_this_topic)  
  
##  <a name="BKMK_Windows_Forms_Applications___NET_"></a> Windows Forms 응용 프로그램 (.NET)  
 **Windows Forms 응용 프로그램 (.NET)** 서식 파일을 만듭니다는 [!INCLUDE[vcprvc](../code-quality/includes/vcprvc_md.md)] Windows Forms 응용 프로그램입니다. 자세한 내용은 [How to: Create a Windows Application Project](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa)을 참조하세요.  
  
 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에서 이 형식의 응용 프로그램을 디버깅하는 방법은 관리되는 Windows Forms 응용 프로그램의 경우와 비슷합니다.  
  
 프로젝트 템플릿을 사용하여 Windows Forms 프로젝트를 만들면 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에서는 디버그 및 릴리스 구성에 필요한 설정을 자동으로 만듭니다. 경우 필요에 따라 변경할 수 있습니다 이러한 설정에는  **\<프로젝트 이름 > 속성 페이지** 대화 상자. 자세한 내용은 참조 [디버그 및 릴리스 구성](../debugger/how-to-set-debug-and-release-configurations.md)합니다.  
  
 자세한 내용은 참조 [c + + 디버그 구성에 대 한 프로젝트 설정을](../debugger/project-settings-for-a-cpp-debug-configuration.md)합니다.  
  
 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 외부에서 응용 프로그램을 시작한 후에 응용 프로그램에 연결하는 방법으로 Windows Forms 응용 프로그램을 디버깅할 수도 있습니다. 자세한 내용은 참조 [실행 중인 프로그램 또는 여러 프로그램에 연결](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md)합니다.  
  
 [항목 내용](../debugger/debugging-preparation-visual-cpp-project-types.md#BKMK_In_this_topic)  
  
## <a name="see-also"></a>참고 항목  
 [Debugger Basics](../debugger/debugger-basics.md) (디버거 기본 사항)  
 [C + + 디버그 구성에 대 한 프로젝트 설정](../debugger/project-settings-for-a-cpp-debug-configuration.md)   
 [실행 중인 프로그램 또는 여러 프로그램에 연결](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md)   
 [디버그 및 릴리스 구성](../debugger/how-to-set-debug-and-release-configurations.md)   
 [방법: Windows 응용 프로그램 프로젝트 만들기](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa)