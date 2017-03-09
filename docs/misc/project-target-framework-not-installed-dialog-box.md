---
title: "프로젝트 대상 프레임워크가 설치되지 않음 대화 상자 | Microsoft Docs"
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
  - "vs.TargetFrameworkNotFound"
ms.assetid: 64ce8743-d5bd-447e-ba10-54b2aafe109e
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# 프로젝트 대상 프레임워크가 설치되지 않음 대화 상자
컴퓨터에 설치되지 않은 프레임워크를 대상으로 하는 프로젝트를 열었습니다. 작업을 계속하려면 이 대화 상자에서 옵션 중 하나를 선택해야 합니다.  
  
> [!NOTE]
>  새 프레임워크를 다운로드하여 설치할 때마다 Visual Studio를 다시 시작해야 합니다.  
  
## Visual Basic 및 Visual C\#  
 Visual Basic 또는 Visual C\# 프로젝트를 연 경우 다음 옵션 중 하나를 선택합니다.  
  
 **대상을 .NET Framework 4.5로 변경합니다.나중에.NET Framework***버전*으로 다시 변경할 수 있습니다.  
 .NET Framework 4.5로 프로젝트 대상을 다시 지정합니다. 나중에 이전 버전을 다시 설치한 다음 프로젝트 대상을 변경할 수 있습니다.  
  
 **.NET Framework \<버전\>의 타기팅 팩을 다운로드합니다. 프로젝트가 변경되지 않습니다.**  
 Microsoft 다운로드 센터 웹사이트를 엽니다. 여기서 원하는 .NET Framework 버전을 다운로드할 수 있습니다. 프로젝트가 솔루션에서 언로드됩니다. 원하는 프레임워크를 다운로드하여 설치한 후에는 Visual Studio를 다시 시작하고 프로젝트를 다시 열어야 합니다.  
  
 **프로젝트를 로드하지 않습니다.**  
 프로젝트를 솔루션에서 언로드된 상태로 둡니다. 나중에 원하는 프레임워크를 설치하고 프로젝트를 다시 로드할 수 있습니다.  
  
## Visual C\+\+  
 Visual C\+\+ 프로젝트를 연 경우 다음 옵션 중 하나를 선택합니다.  
  
 **.NET Framework *버전*의 타기팅 팩을 다운로드합니다 . 프로젝트가 변경되지 않습니다.**  
 Microsoft 다운로드 센터 웹사이트를 엽니다. 여기서 원하는 .NET Framework 버전을 다운로드할 수 있습니다. 다운로드가 완료되면 프로젝트 대상이 해당 버전으로 변경됩니다. 프로젝트가 솔루션에서 언로드됩니다. 원하는 프레임워크를 다운로드하여 설치한 후에는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]를 다시 시작하고 프로젝트를 다시 열어야 합니다.  
  
 **프로젝트를 로드하지 않습니다.**  
 프로젝트를 솔루션에서 언로드된 상태로 둡니다. 나중에 원하는 프레임워크를 설치하고 프로젝트를 다시 로드할 수 있습니다.  
  
## 참고 항목  
 [방법: 한 버전의 .NET Framework를 대상으로 지정](../ide/how-to-target-a-version-of-the-dotnet-framework.md)   
 [.NET Framework 대상 지정 오류 문제 해결](../msbuild/troubleshooting-dotnet-framework-targeting-errors.md)   
 [참조 추가](/visual-cpp/ide/adding-references-in-visual-cpp-projects)