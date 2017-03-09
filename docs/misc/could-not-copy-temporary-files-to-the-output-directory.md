---
title: "임시 파일을 출력 디렉터리에 복사할 수 없습니다. | Microsoft Docs"
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
  - "vs.tasklisterror.cannot_copy_to_run_dir"
ms.assetid: b8b54984-74c9-4b9b-8164-d0d13c141055
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# 임시 파일을 출력 디렉터리에 복사할 수 없습니다.
프로젝트 시스템에서 임시 파일을 출력 디렉터리에 복사할 수 없습니다. 컴파일러는 항상 obj\\`configname`과 같은 중간 디렉터리로 빌드합니다. 빌드 프로세스 마무리 단계에서 프로젝트 시스템은 중간 디렉터리의 파일을 프로젝트 출력 디렉터리로 복사합니다.  
  
 컴파일하는 어셈블리 중 하나가 64KB\(킬로바이트\)보다 크고 다음 조건 중 하나\(또는 둘 다\)에 해당할 때 이 문제가 발생할 수 있습니다.  
  
-   솔루션에 동일한 출력 폴더로 컴파일되는 프로젝트가 포함된 경우  
  
-   참조된 어셈블리 또는 프로젝트 중 하나의 로컬 복사 속성이 False로 설정된 경우  
  
 **이 오류를 해결하려면**  
  
-   개별 프로젝트의 출력을 서로 다른 폴더로 컴파일하세요.  
  
-   참조된 어셈블리 또는 프로젝트의 로컬 복사 속성을 True로 설정하세요.  
  
-   개체 브라우저 창이 열려 있지 않은지 확인하세요.  
  
-   동일한 프로젝트가 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]의 다른 인스턴스에서 열려 있지 않은지 확인하세요.  
  
## 참고 항목  
 [NIB: 방법: 참조의 로컬 복사 속성 설정](http://msdn.microsoft.com/ko-kr/dfe2ba13-f27f-4356-a481-ea67d5acacbd)