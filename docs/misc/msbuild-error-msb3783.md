---
title: "MSBuild 오류 MSB3783 | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "MSBuild.ResolveSDKReference.MaxPlatformVersionLessThanTargetPlatformVersion"
ms.assetid: 847fc96e-73d3-4aa5-927a-ef8cebc8d3f6
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# MSBuild 오류 MSB3783
**MSB3783: MaxPlatformVersion 특성 값이 TargetPlatformVersion 값 "{2}" 보다 작은 "{1}"이기 때문에 "{0}" SDK를 확인할 수 없습니다.**  
  
 MSBuild는 프로젝트에 프로젝트의 대상 플랫폼과 호환되지 않는 종속성이 있을 때 이 오류를 생성합니다.  호환되지 않는 종속성을 사용하면 오류가 발생하거나 런타임에 예기치 않은 응용 프로그램 동작이 발생할 수 있습니다.  
  
### 프로젝트 참조에 대한 오류를 수정하려면  
  
1.  [!INCLUDE[win81](../debugger/includes/win81_md.md)] 스토어 프로젝트를 대상으로 하는 Visual Basic, C\#, C\+\+ 및 JavaScript 프로젝트는 런타임 문제가 발생할 수 있으므로 [!INCLUDE[win8](../debugger/includes/win8_md.md)]을 대상으로 하는 C\+\+ Windows 스토어 프로젝트를 참조할 수 없습니다.  앱의 모든 프로젝트가 [!INCLUDE[win81](../debugger/includes/win81_md.md)]을 대상으로 하여 응용프로그램이 C\+\+ Windows Store 프로젝트로 구성되는 경우 다음 단계를 수행해야 합니다.  
  
2.  앱의 모든 프로젝트 대상을 [!INCLUDE[win81](../debugger/includes/win81_md.md)]로 다시 지정합니다.  이렇게 하려면 앱에서 각 프로젝트를 마우스 오른쪽 단추로 클릭하고 **Windows 8.1로 대상 변경** 명령을 선택한 다음 **프로젝트 및 솔루션 변경 내용 검토** 대화 상자에서 **확인**을 클릭합니다.  
  
3.  C\+\+ Windows 저장소 프로젝트에 따라 각 Visual Basic, C\# 및 JavaScript 프로젝트를 마우스 오른쪽 단추로 클릭하고 **참조 추가**를 선택하여 **Windows** 탭으로 이동한 후 **확장** 하위 탭에서 **Microsoft Visual C\+\+ 런타임 패키지 v11.0**의 선택을 취소하고 **Microsoft Visual C\+\+ 런타임 패키지 v12.0**을 선택한 다음 **확인**을 클릭합니다.  
  
4.  [!INCLUDE[win81](../debugger/includes/win81_md.md)]을 대상으로 하는 Visual Basic, C\# 및 JavaScript Windows 스토어 프로젝트는 [!INCLUDE[win8](../debugger/includes/win8_md.md)] 스토어 프로젝트가 [!INCLUDE[win81](../debugger/includes/win81_md.md)]에서 사용되지 않는 API를 사용하지 않는 경우 [!INCLUDE[win8](../debugger/includes/win8_md.md)]을 대상으로 하는 Visual Basic 및 C\# Windows 스토어 프로젝트를 참조할 수 있습니다.  [!INCLUDE[win8](../debugger/includes/win8_md.md)] 스토어 프로젝트가 [!INCLUDE[win81](../debugger/includes/win81_md.md)] 프로젝트에서 참조될 때 예상대로 작동하는지 여부를 확인하려면 [Windows 8 앱에서 Windows 8.1 Preview로 마이그레이션](http://msdn.microsoft.com/library/windows/apps/dn263113.aspx)을 참조하세요.  
  
     [!INCLUDE[win8](../debugger/includes/win8_md.md)] 스토어 프로젝트는 [!INCLUDE[win81](../debugger/includes/win81_md.md)]을 대상으로 하는 Windows 스토어 프로젝트 또는 이진 파일에 따라 달라질 수 없습니다.  
  
### 확장 SDK 참조에 대한 이 오류를 수정하려면  
  
1.  [!INCLUDE[win81](../debugger/includes/win81_md.md)]을 대상으로 하는 Visual Basic, C\#, C\+\+ 및 JavaScript Windows 스토어 프로젝트는 런타임 문제를 일으키므로 Microsoft Visual C\+\+ 런타임 패키지 v11.0에 종속되는 확장 SDK를 참조할 수 없습니다.  확장 SDK가 Microsoft Visual C\+\+ 런타임 패키지 v11.0에 종속되는지 알아보려면 새 C\# Windows 스토어 프로젝트를 만들고 해당 프로젝트를 마우스 오른쪽 단추로 클릭한 다음 **참조 추가**를 선택하여 **Windows** 탭으로 이동한 후 **확장** 하위 탭에서 확장 SDK를 선택하고 **참조 관리자** 목록의 오른쪽 창에 **Microsoft.VCLibs, 버전 \= 11.0**이 종속성으로 표시되는지 확인합니다.  
  
     [!INCLUDE[win81](../debugger/includes/win81_md.md)]을 대상으로 하는 Visual Basic, C\# 및 JavaScript Windows 스토어 프로젝트는 이러한 확장 SDK가 [!INCLUDE[win81](../debugger/includes/win81_md.md)]에서 사용되지 않는 API를 사용하지 않는 경우 Microsoft Visual C\+\+ 런타임 패키지 v11.0에 종속되지 않는 확장 SDK를 참조할 수 있습니다.  [!INCLUDE[win81](../debugger/includes/win81_md.md)]을 대상으로 하는 저장소 프로젝트에서 확장 SDK를 참조할 수 있는지 확인하려면 해당 확장 SDK의 공급업체 사이트를 참조하세요.  
  
     앱에서 참조하는 확장 SDK가 지원되지 않는 경우 다음 단계를 수행해야 합니다.  
  
2.  오류를 일으키는 프로젝트의 이름을 확인합니다.  프로젝트의 대상 플랫폼이 프로젝트 이름 옆의 괄호 안에 표시됩니다.  예를 들어 **MyProjectName \(Windows 8.1\)**은 MyProjectName 프로젝트가 플랫폼 버전 [!INCLUDE[win81](../debugger/includes/win81_md.md)]을 대상으로 한다는 것을 의미합니다.  
  
3.  지원되지 않는 확장 SDK를 소유한 공급업체의 사이트로 이동하여 프로젝트의 대상 플랫폼 버전과 호환되는 종속성으로 확장 SDK 버전을 설치합니다.  
  
4.  이전에 설치한 확장 SDK가 다른 확장 SDK에 종속된 경우 종속성을 소유한 공급업체의 사이트로 이동하여 프로젝트의 대상 플랫폼 버전과 호환되는 종속성 버전을 설치합니다.  
  
    > [!NOTE]
    >  프로젝트가 [!INCLUDE[win81](../debugger/includes/win81_md.md)]을 대상으로 하고 이전에 설치된 확장 SDK가 Microsoft Visual C\+\+ 런타임 패키지에 종속된 경우 Windows 8.1과 호환되는 Microsoft Visual C\+\+ 런타임 패키지의 버전은 v12.0이고 [!INCLUDE[vs_dev12](../data-tools/includes/vs_dev12_md.md)]과 함께 설치됩니다.  
  
    > [!NOTE]
    >  다른 확장 SDK에 대한 종속성이 있는 이전에 설치된 확장 SDK에서 Visual Studio를 다시 시작할지 여부를 확인하려면 새 C\# Windows 스토어 프로젝트를 만들고 프로젝트를 마우스 오른쪽 단추를 클릭한 후 **참조 추가**를 선택하여 **Windows** 탭의 **확장** 하위 탭으로 이동한 후 확장 SDK를 선택하고 **참조 관리자**의 오른쪽 창을 확인합니다.  종속성이 있는 경우 나열됩니다.  
  
5.  Visual Studio를 다시 시작하고 앱을 엽니다.  
  
6.  오류를 일으키는 프로젝트를 마우스 오른쪽 단추로 클릭하고 Visual Basic, C\# 또는 JavaScript 프로젝트의 경우 **참조 추가**, C\+\+ 프로젝트의 경우 **참조**를 선택합니다.  그런 다음 C\+\+ 프로젝트의 경우 새 참조 추가 단추를 클릭합니다.  
  
7.  **Windows** 탭을 클릭한 다음 **확장** 하위 탭을 클릭합니다.  이전 확장 SDK 옆에 있는 확인란의 선택을 취소하고 새 확장 SDK 옆의 확인란을 선택합니다.  **확인**을 클릭합니다.