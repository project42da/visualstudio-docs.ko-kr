---
title: "&lt;이름&gt; 프로젝트를 현재 프로젝트 형식으로 변환해야 합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/24/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.Conversion7"
  - "vs.UpgradeWarningDlg"
ms.assetid: e27d58e5-c270-468b-bb98-3163d40900bc
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# &lt;이름&gt; 프로젝트를 현재 프로젝트 형식으로 변환해야 합니다.
이전 버전의 Visual Studio에서 만든 프로젝트를 열었습니다. 컴퓨터에 설치된 Visual Studio 버전에서 프로젝트를 열어 편집하려면 먼저 프로젝트 파일을 현재 형식으로 변환해야 합니다. 이 프로젝트를 지금 변환할지 여부는 선택할 수 있지만 형식 변환 작업을 취소할 수는 없습니다.  
  
> [!CAUTION]
>  프로젝트가 소스 코드 제어에 저장되어 있는 경우 변환된 프로젝트를 다시 체크 인하려면 먼저 다른 솔루션에서 해당 프로젝트를 공유하고 있는지 확인하세요. 새로 변환된 프로젝트가 변환되지 않은 다른 솔루션에서 사용되고 있는 경우에는 이 프로젝트를 체크 인하지 마세요. 체크 인하면 솔루션의 종속 관계가 해제되고 솔루션을 제대로 열거나 빌드할 수 없게 됩니다.  
  
 프로젝트 파일을 변환하기 전에 백업본을 만들 수도 있습니다.  
  
> [!NOTE]
>  Visual C\+\+ 프로젝트 같은 특정 프로젝트 형식이 변환되면 이전 프로젝트 파일은 .old 확장명으로 표시되고 프로젝트 디렉터리에 저장됩니다.  
  
 읽기 전용 프로젝트는 변환되지 않습니다. 이러한 프로젝트는 편집 권한이 있는 사용자만 변환할 수 있습니다. 변환된 솔루션에서 프로젝트를 사용하려면 먼저 프로젝트 파일을 현재 형식으로 변환해야 합니다. 프로젝트를 변환한 후에는 이전 버전의 Visual Studio에서 만든 프로젝트를 포함하는 솔루션을 더 이상 편집하거나 빌드하거나 실행할 수 없습니다.  
  
### 이 메시지에 응답하려면  
  
1.  **예** 또는 **아니요**를 선택합니다.  
  
    -   **예** \- 프로젝트를 편집할 수 있는 경우 컴퓨터에 설치된 Visual Studio 버전에서 사용하는 형식으로 변환됩니다. 변환된 프로젝트가 소스 코드 제어에 저장되어 있는 경우에는 편집할 수 있도록 로컬 드라이브에 체크 아웃되어 열립니다.  
  
    -   **아니요** \- 프로젝트가 변환되지 않고 소스 코드 제어에서 체크 아웃되지 않으므로 열리지 않습니다.  
  
 개발 팀의 일원인 경우 프로젝트에 대해 작업 중인 모든 사람의 로컬 컴퓨터에 같은 버전의 Visual Studio가 설치되어 있어야 합니다. 프로젝트에 대한 액세스 권한을 계속 유지하려면 개발 팀에 정기적으로 문의하세요.  
  
## 참고 항목  
 [Project Dependencies Dialog Box](http://msdn.microsoft.com/ko-kr/d66e48c3-3722-40dd-99b4-53d93cac128e)   
 [Visual Studio에서 응용 프로그램　빌드](../ide/compiling-and-building-in-visual-studio.md)