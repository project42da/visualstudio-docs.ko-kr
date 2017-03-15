---
title: "How to: Add an Application Configuration File to a C# Project | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "app.config files, adding to C# projects"
ms.assetid: 9caf6bb0-c2fc-4ab6-ba69-bed3b880fbf8
caps.latest.revision: 20
caps.handback.revision: 20
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# How to: Add an Application Configuration File to a C# Project
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

C\# 프로젝트에는 응용 프로그램 구성 파일 \(app.config 파일\)을 추가 하 여 공용 언어 런타임 찾아 어셈블리 파일 로드 하는 사용자 지정할 수 있습니다.  응용 프로그램 구성 파일에 대한 자세한 내용은 [런타임에서 어셈블리를 찾는 방법](../Topic/How%20the%20Runtime%20Locates%20Assemblies.md)을 참조하십시오.  
  
> [!NOTE]
>  Windows 저장소를 지원 하지 않는 <xref:System.Configuration>.  결과적으로 저장소 응용 프로그램의 app.config 템플릿을 포함 되지 않습니다.  
  
 프로젝트를 빌드할 때 개발 환경 app.config 파일을 자동으로 복사 실행 파일에 일치 하는 복사본의 파일 이름 변경 및 다음 복사본을 bin 디렉터리로 이동 합니다.  
  
### C\# 프로젝트에 응용 프로그램 구성 파일을 추가하려면  
  
1.  메뉴 모음에서 선택  **프로젝트**,  **새 항목 추가**.  
  
     **새 항목 추가** 대화 상자가 나타납니다.  
  
2.  확장  **설치 된**, 확장  **C\# 항목 Visual**, 다음 선택의  **응용 프로그램 구성 파일** 템플릿.  
  
3.  에  **이름** 텍스트 상자에 이름을 입력 한 다음 선택 된  **추가** 단추.  
  
     App.config 라는 파일을 프로젝트에 추가 됩니다.  
  
## 참고 항목  
 [응용 프로그램 설정 관리\(.NET\)](../ide/managing-application-settings-dotnet.md)   
 [구성 파일 스키마](../Topic/Configuration%20File%20Schema%20for%20the%20.NET%20Framework.md)   
 [응용 프로그램 구성](../Topic/Configuring%20Apps%20by%20using%20Configuration%20Files.md)   
 [How to: Configure an App to Target a .NET Framework Version](http://msdn.microsoft.com/ko-kr/5247b307-89ca-417b-8dd0-e8f9bd2f4717)   
 [Using the Visual C\# Development Environment](../csharp-ide/using-the-visual-studio-development-environment-for-csharp.md)