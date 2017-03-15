---
title: "MSBuild 오류 MSB3187 | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "MSBuild.GenerateManifest.PlatformMismatch"
helpviewer_keywords: 
  - "MSB3187"
ms.assetid: c5e93c14-b099-4176-bf1b-dbecc47fb3fd
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# MSBuild 오류 MSB3187
**MSB3187: 참조된 어셈블리 '\<assembly\>'이\(가\) 응용 프로그램과 다른 프로세서를 대상으로 합니다.**  
  
 이 경고는 응용 프로그램의 대상 플랫폼\(프로세서 아키텍처\)이 중립\(MSIL\)으로 설정되어 있지만 참조된 어셈블리가 중립이 아닌 경우 또는 응용 프로그램의 아키텍처가 중립이 아니지만 종속 항목이 중립인 경우 발생합니다.  두 항목이 모두 플랫폼 중립이 아닌 경우에는 아키텍처가 일치해야 합니다.  또한 응용 프로그램 아키텍처와 진입점 어셈블리 아키텍처도 항상 일치해야 합니다.  
  
### 이 오류를 해결하려면  
  
-   응용 프로그램의 대상 플랫폼\(프로세서 아키텍처\)이 참조된 모든 어셈블리 및 진입점 어셈블리 아키텍처와 일치하는지 확인합니다.  
  
## 참고 항목  
 [고급 컴파일러 설정 대화 상자\(Visual Basic\)](../ide/reference/advanced-compiler-settings-dialog-box-visual-basic.md)   
 [프로젝트 디자이너, 빌드 페이지\(C\#\)](../ide/reference/build-page-project-designer-csharp.md)