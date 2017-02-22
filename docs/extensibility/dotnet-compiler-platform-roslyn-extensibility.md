---
title: ".NET 컴파일러 플랫폼 (&quot;Roslyn&quot;)의 확장성 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 564201b3-1e18-4b88-b615-42c2f57f3fe8
caps.latest.revision: 4
caps.handback.revision: 4
ms.author: "gregvanl"
manager: "ghogen"
---
# .NET 컴파일러 플랫폼 (&quot;Roslyn&quot;)의 확장성
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

.NET 컴파일러 플랫폼 \("Roslyn"\)의 핵심 업무는 C\# 및 Visual Basic 컴파일러를 열어 도구로 및 프로그램에 대 한 풍부한 정보 컴파일러에서 공유 하는 개발자가 있습니다. 코드 분석 도구는 코드 품질 향상 및 코드 생성기는 응용 프로그램을 만드는 데 유용 합니다. 도구 들 보다 효율적인만 컴파일러 소유 하는 전체 코드 지식에 등 액세스할 필요 합니다. 불투명 변환기 \(소스 코드 및 개체 코드\) 되 고, 대신 Roslyn 컴파일러는 도구와 응용 프로그램의 코드 관련 작업에 대해 사용할 수 있는 Api를 제공 합니다.  
  
 가장 좋은 점은 Roslyn 컴파일러, Api, 샘플 및 연습 및 이러한 Api를 기반으로 구축 된 실제 도구에서 완벽 하 게 오픈 소스는 [github.com\/dotnet\/roslyn](https://github.com/dotnet/Roslyn)합니다. Roslyn 시작 하 고 자세한 OSS 사이트로 이동 하십시오. Roslyn Api를 활용 하는 도구 작성기로 작업 시작에 대 한 링크 뿐 아니라 최신 C\# 및 최종 사용자로 사용할 수 있는 VB 기능을 다운로드할 수 있는 링크를 찾을 수 있습니다.  
  
## 참고 항목  
 [Roslyn 분석기를 시작 하기](../extensibility/getting-started-with-roslyn-analyzers.md)