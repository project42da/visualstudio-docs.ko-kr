---
title: "Roslyn 분석기를 시작 하기 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 367c2ec8-3059-46a5-9d1c-57bead0419e7
caps.latest.revision: 6
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 6
---
# Roslyn 분석기를 시작 하기
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Visual Studio에서 라이브, 프로젝트 기반 코드 분석기를 사용 하 여 API 작성자의 NuGet 패키지의 일부로 도메인 관련 코드 분석을 제공 수 있습니다.  이 분석기는.NET 컴파일러 플랫폼 \(코드 이름된 "Roslyn"\)에서 구동 되, 때문에 \(문제를 발견 하 여 코드를 빌드합니다 더 이상 대기\) 줄을 완료 했으면 전에 입력할 때 코드에서 경고가 생성 될 수 있습니다.  분석기 수 있도록 코드를 정리 즉시 Visual Studio 전구 프롬프트를 통해 자동 코드 수정 프로그램 화면도 수 있습니다.  
  
## 시작  
 [Roslyn 라이브 코드 분석기 소개 및 연습](https://msdn.microsoft.com/en-us/magazine/dn879356.aspx)  
  
 [분석기 문제에 대 한 사용자가 수정 제공 adding 코드 연습을 수정 합니다.](https://msdn.microsoft.com/en-us/magazine/dn904670.aspx)  
  
 [소개 및 실제 분석기 이야기가 연습](http://channel9.msdn.com/events/Build/2015/3-725)  
  
 [실제 Roslyn 분석기](../extensibility/roslyn-analyzers-and-code-aware-library-for-immutablearrays.md) 로 볼 수 있도록 [이야기](http://channel9.msdn.com/events/Build/2015/3-725)  
  
 [그룹화 된 세 가지 유형의 분석기 github에서 몇 가지 예제](https://github.com/dotnet/roslyn/blob/master/docs/analyzers/Analyzer%20Samples.md)  
  
 [소개와 몇 가지 분석기의 이야기](http://channel9.msdn.com/Events/dotnetConf/2015/NET-Compiler-Platform-Roslyn-Analyzers-and-the-Rise-of-Code-Aware-Libraries)  
  
## 기타 리소스  
 [OSS github 사이트에서 더 많은 문서](https://github.com/dotnet/roslyn/tree/master/docs/analyzers)  
  
 [Github에서 Roslyn 분석기를 사용 하 여 구현 하는 FxCop 규칙](https://github.com/dotnet/roslyn/tree/master/src/Diagnostics/FxCop)