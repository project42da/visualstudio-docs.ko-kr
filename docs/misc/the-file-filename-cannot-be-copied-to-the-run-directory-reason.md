---
title: "&#39;filename&#39; 파일을 실행 디렉터리로 복사할 수 없습니다. &lt;이유&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.tasklisterror.cant_copy_to_run_dir"
ms.assetid: 80474e62-7cef-48e9-a7c0-820345d5b591
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# &#39;filename&#39; 파일을 실행 디렉터리로 복사할 수 없습니다. &lt;이유&gt;
이 오류가 표시 되는 경우:  
  
-   `true`에 대해 설정된 `CopyLocal` 속성을 가진 참조\(솔루션 탐색기에서 참조를 선택했을 때 속성 창 확인\)을 프로젝트를 실행하는 디렉터리로 복사할 수 없습니다.  
  
-   `true`에 대해 설정된 `CopyLocal` 속성을 가진 참조의 종속성을 프로젝트를 실행하는 디렉터리로 복사할 수 없습니다.  
  
-   로컬로 복사해야 하는 그 외 파일을 프로젝트를 실행하는 디렉터리로 복사할 수 없습니다.  
  
 보통은 오류 메시지 하단의 `reason`에서 다른 프로세스가 해당 파일을 사용 중인 것을 알 수 있습니다. 해당 파일이 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에서 다른 작업에 의해 잠겨 있을 가능성이 있습니다.  
  
 프로젝트를 동일한 출력 디렉터리에 빌드하는 것과 관련된 문제가 있을 수 있습니다. 이 경우 두 프로젝트를 다른 디렉터리에 빌드합니다. 다른 디렉터리로 빌드할 경우 프로젝트 시스템이 모든 종속 어셈블리를 프로젝트의 출력 디렉터리로 복사합니다.  
  
 작업 중인 프로젝트의 출력을 도구 상자 항목으로 추가하면 관리되는 설계자가 참조를 잠그게 됩니다.  
  
 출력이 현재 실행 중이면 프로젝트 시스템이 출력 디렉터리를 업데이트할 수 없습니다.  
  
 **이 오류를 해결하려면**  
  
-   컴퓨터의 사용 가능한 디스크 공간 확인  
  
-   파일 시스템에서 적용하는 MAX\_PATH 제한에 도달했는지 확인  
  
     그렇다고 프로젝트 빌드를 할 수 없는 것은 아닙니다. 하지만 이는 참조된 어셈블리의 개인 복사본이 제대로 업데이트될 수 없음을 나타내는 경고이므로 프로젝트 실행을 못하게 될 수 있습니다. 프로젝트가 실행되는 것처럼 보여도 특정 코드 경로를 실행할 때 형식 로드 예외 오류 또는 기타 예기치 않은 동작이 발생할 수 있습니다.  
  
## 참고 항목  
 [NIB: 방법: 참조의 로컬 복사 속성 설정](http://msdn.microsoft.com/ko-kr/dfe2ba13-f27f-4356-a481-ea67d5acacbd)