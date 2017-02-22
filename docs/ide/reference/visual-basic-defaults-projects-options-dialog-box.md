---
title: "옵션 대화 상자, 프로젝트, VB 기본값 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VS.ToolsOptionsPages.Projects.VBDefaults"
helpviewer_keywords: 
  - "Option Explicit 문, IDE에서 설정"
  - "Option Compare 문, IDE에서 설정"
  - "Option Strict 문, IDE에서 설정"
ms.assetid: 2465cd9d-18b6-4c4a-b1ea-86dbab23fc79
caps.latest.revision: 19
caps.handback.revision: 19
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# 옵션 대화 상자, 프로젝트, VB 기본값
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

Visual Basic 프로젝트 옵션의 기본 설정을 지정합니다.  새 프로젝트를 만들면 지정한 옵션 문이 코드 편집기의 프로젝트 헤더에 추가됩니다.  이 옵션은 모든 Visual Basic 프로젝트에 적용됩니다.  
  
 이 대화 상자에 액세스하려면 **도구** 메뉴에서 **옵션**을 클릭한 다음 **프로젝트 및 솔루션** 폴더를 확장하고 **VB 기본값**을 클릭합니다.  
  
 **Option Explicit**  
 변수를 명시적으로 선언하도록 컴파일러 기본값을 설정합니다.  기본적으로 **Option Explicit**은 **On**으로 설정되어 있습니다.  자세한 내용은 [\/optionexplicit](/dotnet/visual-basic/reference/command-line-compiler/optionexplicit)를 참조하십시오.  
  
 **Option Strict**  
 명시적 축소 변환을 수행하고 런타임에 바인딩을 허용하지 않도록 컴파일러 기본값을 설정합니다.  기본적으로 **Option Strict**는 **Off**로 설정되어 있습니다.  자세한 내용은 [\/optionstrict](/dotnet/visual-basic/reference/command-line-compiler/optionstrict)를 참조하십시오.  
  
 **Option Compare**  
 문자열 비교에 대한 컴파일러 기본값을 Binary\(대\/소문자 구분\) 또는 Text\(대\/소문자 구분 안 함\)로 설정합니다. 기본적으로 **Option Compare**는 **Binary**로 설정되어 있습니다.  자세한 내용은 [\/optioncompare](/dotnet/visual-basic/reference/command-line-compiler/optioncompare)를 참조하십시오.  
  
 **Option Infer**  
 지역 형식 유추에 대한 컴파일러 기본값을 설정합니다.  기본적으로 **Option Infer**는 새로 만든 프로젝트에 대해서는 **On**으로, 그리고 이전 버전의 Visual Basic에서 만든 마이그레이션된 프로젝트에 대해서는 **Off**로 설정됩니다.  자세한 내용은 [\/optioninfer](/dotnet/visual-basic/reference/command-line-compiler/optioninfer)를 참조하십시오.  
  
## 참고 항목  
 [솔루션 및 프로젝트](../../ide/solutions-and-projects-in-visual-studio.md)