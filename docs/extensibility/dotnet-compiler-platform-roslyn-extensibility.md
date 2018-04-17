---
title: .NET 컴파일러 플랫폼 (&quot;Roslyn&quot;) 확장성 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
ms.assetid: 564201b3-1e18-4b88-b615-42c2f57f3fe8
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 09287c48285bfcdc32b1a7d558d44f9d212f1b41
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="net-compiler-platform-quotroslynquot-extensibility"></a>.NET 컴파일러 플랫폼 (&quot;Roslyn&quot;) 확장성
.NET 컴파일러 플랫폼 ("Roslyn")의 핵심 업무는 C# 및 Visual Basic 컴파일러를 열면 및 도구를 허용 하 고 프로그램에 대 한 풍부한 정보 컴파일러에서 공유 하는 개발자가 있습니다. 코드 분석 도구 코드의 품질을 향상 되 고 응용 프로그램 생성의 생성기 지원 코드. 도구 빈틈을 가져오려면를 점점 더만 컴파일러 소유 하는 하위 코드 지식의 액세스할 필요 있습니다. 불투명 변환기 (소스 코드와 아웃 개체 코드) 않고 Roslyn 컴파일러는 도구 및 응용 프로그램의 코드 관련 작업에 대해 사용할 수 있는 Api를 제공 합니다.  
  
 가장 중요 한 부분은 Roslyn 컴파일러, 해당 Api, 샘플 및 연습 및 이러한 Api를 기반으로 빌드된 실제 도구에서 완벽 하 게 오픈 소스 않는다는 [github.com/dotnet/roslyn](https://github.com/dotnet/Roslyn)합니다. Roslyn 시작 하 고 자세한 OSS 사이트로 이동 하십시오. Roslyn Api를 활용 하는 도구 작성기로 작업 시작에 대 한 링크 뿐 아니라 최신 C# 및 최종 사용자로 사용할 수 있는 VB 기능을 다운로드할 수 있는 링크를 찾을 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [Roslyn 분석기 시작](../extensibility/getting-started-with-roslyn-analyzers.md)