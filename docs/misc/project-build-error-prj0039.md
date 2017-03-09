---
title: "프로젝트 빌드 오류 PRJ0039 | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "PRJ0039"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PRJ0039"
ms.assetid: 207bbc28-922f-44d6-8bdd-3016c850f5b9
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "douge"
---
# 프로젝트 빌드 오류 PRJ0039
임시 파일을 만들 수 없습니다. NMake 도구를 실행하려면 임시 파일을 만들 수 있어야 합니다.  
  
 메이크파일 프로젝트를 빌드하는 경우\([메이크파일 프로젝트 만들기](/visual-cpp/ide/creating-a-makefile-project) 참조\) Visual C\+\+ 프로젝트 시스템에서 일부 임시 파일을 만들어야 합니다. 이 오류는 프로젝트 시스템에서 해당 파일을 하나 이상 만들 수 없다는 것을 나타냅니다.  
  
 TMP 환경 변수에 임시 디렉터리의 이름이 들어 있습니다.  
  
 이 오류의 가능한 원인 및 권장된 해결 방법은 아래 나와 있습니다.  
  
 사용자에게 임시 디렉터리에 대한 쓰기 권한이 없습니다.  
 임시 디렉터리에 대한 쓰기 권한이 있는지 확인합니다.  
  
 임시 디렉터리에 너무 많은 임시 파일이 있습니다.  
 다른 프로세스에서 임시 파일을 만들었을 수 있지만 삭제하지 못했을 수 있습니다. 이러한 임시 파일 일부 또는 모두를 삭제합니다.  
  
 여유 디스크 공간이 없습니다.  
 디스크에서 일부 파일을 삭제하거나 임시 디렉터리를 여유 공간이 있는 디스크로 변경합니다.  
  
 TMP 환경 변수가 잘못되었습니다.  
 TMP 환경 변수가 존재하지 않는 디렉터리를 가리킬 수도 있습니다.