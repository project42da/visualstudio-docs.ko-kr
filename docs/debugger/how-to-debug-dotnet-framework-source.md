---
title: "방법: .NET Framework 소스 디버깅 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "FSharp"
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "디버깅, .NET Framework 소스"
ms.assetid: fc12e472-ac6a-4e77-8e22-a769e13a03b8
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# 방법: .NET Framework 소스 디버깅
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 최신 버전에는 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 디버깅을 위한 새로운 기능이 제공됩니다.  [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 소스를 디버깅하려면 코드에 대한 디버깅 기호에 액세스할 수 있어야 하며  [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 소스 한 단계씩 실행도 설정되어 있어야 합니다.  
  
 **옵션** 대화 상자에서 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 단계별 실행 및 기호 다운로드를 설정할 수 있습니다.  기호 다운로드를 설정할 때 기호를 즉시 다운로드할 수도 있고 나중에 다운로드하도록 옵션만 설정해 놓을 수도 있습니다.  기호를 즉시 다운로드하지 않으면 기호는 다음 번에 응용 프로그램 디버깅을 시작할 때 다운로드됩니다.  **모듈** 창 또는 **호출 스택** 창에서 수동으로 다운로드할 수도 있습니다.  
  
### .NET Framework 소스 디버깅을 사용하려면  
  
1.  **도구** 메뉴에서 **옵션**을 클릭합니다.  
  
2.  **옵션** 대화 상자에서 **디버깅** 범주를 선택합니다.  
  
3.  **일반** 상자에서 **.NET Framework 소스 단계별 실행 사용**을 설정합니다.  
  
    1.  내 코드만을 사용하는 경우에는 내 코드만을 이제 사용하지 않는다는 경고 대화 상자가 표시됩니다.  **확인**을 클릭합니다.  
  
    2.  기호 캐시 위치가 설정되어 있지 않으면 기본 기호 캐시 위치가 이제 설정된다는 또 다른 경고 대화 상자가 표시됩니다.  **확인**을 클릭합니다.  
  
4.  **디버깅** 범주 아래에서 **기호**를 클릭합니다.  
  
5.  기호 캐시 위치를 변경하려면:  
  
    1.  왼쪽 상자에서 **디버깅** 노드를 엽니다.  
  
    2.  **디버깅** 노드 아래에서 **기호**를 클릭합니다.  
  
    3.  **기호 서버에서 이 디렉터리로 기호 캐시**에서 위치를 편집하거나 **찾아보기**를 클릭하여 위치를 선택합니다.  
  
6.  기호를 즉시 다운로드하려면 **위의 위치에서 기호 로드**를 클릭합니다.  
  
     이 단추는 디자인 모드에서 사용할 수 없습니다.  
  
     지금 기호를 다운로드하도록 선택하지 않으면 다음 번 프로그램 디버깅을 시작할 때 기호가 자동으로 다운로드됩니다.  
  
7.  **확인**을 클릭하여 **옵션** 대화 상자를 닫습니다.  
  
### 모듈 창을 사용하여 Framework 기호를 로드하려면  
  
1.  **모듈** 창에서 기호가 로드되지 않은 모듈을 마우스 오른쪽 단추로 클릭합니다.  **기호 상태** 열을 보면 기호가 로드되었는지 여부를 확인할 수 있습니다.  
  
2.  **다음에서 기호 로드**를 가리키고 **Microsoft 공용 기호 서버**를 클릭하여 Microsoft 공용 기호 서버에서 기호를 다운로드하거나 **기호 경로**를 클릭하여 이전에 기호를 저장한 디렉터리에서 기호를 로드합니다.  
  
### 호출 스택 창을 사용하여 Framework 기호를 로드하려면  
  
1.  **호출 스택** 창에서 기호가 로드되지 않은 프레임을 마우스 오른쪽 단추로 클릭합니다.  프레임이 흐리게 표시됩니다.  
  
2.  **다음에서 기호 로드**를 가리킨 다음 **Microsoft 공용 기호 서버** 또는 **기호 경로**를 클릭합니다.  
  
## 참고 항목  
 [관리 코드 디버깅](../debugger/debugging-managed-code.md)   
 [기호 파일\(.pdb\) 및 원본 파일 지정](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)