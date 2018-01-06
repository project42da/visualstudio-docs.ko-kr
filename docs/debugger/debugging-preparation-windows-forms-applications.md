---
title: "디버깅 준비: Windows Forms 응용 프로그램 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging Windows applications
- Windows applications, debugging
- debugging [Visual Studio], Windows applications
- debugging [C#], Windows applications
- debugging [Visual Basic], Windows applications
ms.assetid: 7092ee7f-8378-4def-aef8-1695bd97cf14
caps.latest.revision: "28"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 01e9b9ced1db8f41c8ad1fb6386eec0d6080dd99
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="debugging-preparation-windows-forms-applications"></a>디버깅 준비: Windows Forms 응용 프로그램
Windows Forms 프로젝트 템플릿은 Windows Forms 응용 프로그램을 만듭니다. 이러한 형식의 응용 프로그램은 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에서 쉽게 디버깅할 수 있습니다. 자세한 내용은 참조 [Windows 응용 프로그램 프로젝트 만들기](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa)합니다.  
  
 프로젝트 템플릿을 사용하여 Windows Forms 프로젝트를 만들면 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에서는 디버그 및 릴리스 구성에 필요한 설정을 자동으로 만듭니다. 필요하면 이 설정을 변경할 수 있습니다. 이러한 설정을 변경할 수 있습니다는  **\<프로젝트 이름 > 속성 페이지** 대화 상자 (**My Project** Visual basic에서).  
  
 자세한 내용은 참조 [권장 속성 설정](../debugger/managed-debugging-recommended-property-settings.md)합니다.  
  
 다음 표에서는 권장 속성 설정을 하나 더 보여 줍니다.  
  
### <a name="configuration-properties-in-debug-tab"></a>디버그 탭의 구성 속성  
  
|**속성 이름**|**설정**|  
|-----------------------|-----------------|  
|**시작 작업**|-로 설정 합니다. **프로젝트 시작** 대부분의 경우. 로 설정 **시작 외부 프로그램** 다른 실행을 시작 하려는 경우 시작할 때 디버깅 (일반적으로 Dll 디버깅) 합니다.|  
  
 Windows Forms 응용 프로그램을 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 내에서 디버깅하거나 이미 실행 중인 응용 프로그램에 연결하여 디버깅할 수 있습니다. 연결에 대 한 자세한 내용은 참조 [실행 중인 프로세스에 연결할](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md)합니다.  
  
### <a name="to-debug-a-c-f-or-visual-basic-windows-forms-application"></a>C#, F# 또는 Visual Basic Windows Forms 응용 프로그램을 디버깅하려면  
  
1.  [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에서 프로젝트를 엽니다.  
  
2.  필요한 중단점을 만듭니다.  
  
     Windows Forms 응용 프로그램은 이벤트 구동 응용 프로그램이므로 중단점은 이벤트 처리기 코드에 배치되거나 이벤트 처리기 코드에서 호출하는 메서드에 배치됩니다. 중단점이 배치되는 일반적인 이벤트는 다음과 같습니다.  
  
    1.  Click, Enter 같이 컨트롤에 연결된 이벤트  
  
    2.  Load, Activated 같이 응용 프로그램 시작 및 종료에 연결된 이벤트  
  
    3.  포커스 및 유효성 검사 이벤트  
  
     자세한 내용은 [Windows Forms에서 이벤트 처리기 만들기](/dotnet/framework/winforms/creating-event-handlers-in-windows-forms)를 참조하세요.  
  
3.  에 **디버그** 메뉴를 클릭 하 여 **시작**합니다.  
  
4.  에 설명 된 기술을 사용 하 여 디버깅 [디버거 기본 사항](../debugger/debugger-basics.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Debugging Managed Code](../debugger/debugging-managed-code.md) (관리 코드 디버그)  
 [C#, F# 및 Visual Basic 프로젝트 형식](../debugger/debugging-preparation-csharp-f-hash-and-visual-basic-project-types.md)   
 [방법: 디버그 및 릴리스 구성](../debugger/how-to-set-debug-and-release-configurations.md)   
 [C# 디버그 구성을 위한 프로젝트 설정](../debugger/project-settings-for-csharp-debug-configurations.md)   
 [Visual Basic 디버그 구성을 위한 프로젝트 설정](../debugger/project-settings-for-a-visual-basic-debug-configuration.md)   
 [실행 중인 프로세스에 연결](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md)   
 [Windows Forms](/dotnet/framework/winforms/index)