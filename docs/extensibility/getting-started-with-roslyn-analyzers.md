---
title: Roslyn 분석기를 시작 | Microsoft Docs
ms.date: 04/02/2018
ms.technology: vs-ide-sdk
ms.topic: conceptual
ms.assetid: 367c2ec8-3059-46a5-9d1c-57bead0419e7
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 7b887703343dab10f9cc1f0cbf8e2e2b37b0065b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="getting-started-with-roslyn-analyzers"></a>Roslyn 분석기를 시작 하기

Visual Studio에서 라이브, 프로젝트 기반 코드 분석기, API 작성자 NuGet 패키지의 일부로 도메인 관련 코드 분석을 제공할 수 있습니다. .NET 컴파일러 플랫폼 (코드 이름된 "Roslyn"), 이러한 분석기 기반의 때문에 (더 이상 대기 중 문제를 발견 하 여 코드를 빌드하려면) 줄 모두 읽었으면 전에 입력할 때 코드에서 경고가 생성 될 수 있습니다. 분석기 수 있도록 코드를 정리 즉시 Visual Studio 전구 프롬프트를 통해 자동 코드 수정 프로그램 발생할 수도 수 있습니다.

## <a name="getting-started"></a>시작

[Roslyn 라이브 코드 분석기 및 해결 방법 소개](https://msdn.microsoft.com/magazine/dn879356.aspx)

[분석기 문제에 대 한 사용자가 수정 제공 코드 해결 연습 adding:](https://msdn.microsoft.com/magazine/dn904670.aspx)

[소개 및 실제 분석기 Talk의 연습](http://channel9.msdn.com/events/Build/2015/3-725)

[실제 세계 Roslyn 분석기](../extensibility/roslyn-analyzers-and-code-aware-library-for-immutablearrays.md) 으로 볼 수 있도록는 [와 통신](http://channel9.msdn.com/events/Build/2015/3-725)

[세 가지 분석기로 그룹화 된 github의 몇 가지 예제](https://github.com/dotnet/roslyn/blob/master/docs/analyzers/Analyzer%20Samples.md)

[소개 및 몇 가지 분석기 둘러보기 말](http://channel9.msdn.com/Events/dotnetConf/2015/NET-Compiler-Platform-Roslyn-Analyzers-and-the-Rise-of-Code-Aware-Libraries)

## <a name="see-also"></a>참고자료

- [Roslyn 분석기 개요](../code-quality/roslyn-analyzers-overview.md)
- [OSS github 사이트에서 더 많은 docs](https://github.com/dotnet/roslyn/tree/master/docs/analyzers)
- [Github의 Roslyn 분석기를 사용 하 여 구현 FxCop 규칙](https://github.com/dotnet/roslyn/tree/master/src/Diagnostics/FxCop)