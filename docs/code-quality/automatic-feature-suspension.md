---
title: "자동 기능 일시 중단이 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- full solution analysis
- performance
- low-memory
ms.assetid: 572c15aa-1fd0-468c-b6be-9fa50e170914
caps.latest.revision: "6"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-ide-code-analysis
ms.openlocfilehash: a2c836364092aa71f40d4d7aa4566b2d12def00e
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="automatic-feature-suspension"></a>자동 기능 일시 중단
사용 가능한 시스템 메모리 200MB 이하로 떨어지면, Visual Studio 코드 편집기에서 다음 메시지를 표시 합니다.  
  
 ![전체 솔루션 분석 사용 중단 경고 텍스트](../code-quality/media/fsa_alert.png "FSA_Alert")  
  
 Visual Studio에서 검색 하는 메모리 부족 상태를 안정적으로 유지 하기 위해 특정 고급 기능이 자동으로 중단 합니다. 이러한 고급 기능 일시 중단 경고가 표시 됩니다, 그리고 Visual Studio 이전 처럼 작동 하도록 계속 하지만 성능이 약간 저하 됩니다.  
  
 메모리 부족 상태에서 다음 작업이 수행 됩니다.  
  
-   Visual C# 및 Visual Basic에 대 한 전체 솔루션 분석 사용 되지 않습니다.  
  
-   [가비지 수집](/dotnet/standard/garbage-collection/index) Visual C# 및 Visual Basic에 대 한 낮은 대기 시간 모드 (GC) 사용할 수 없습니다.  
  
-   Visual Studio 캐시가 플러시됩니다.  
  
## <a name="improve-visual-studio-performance"></a>Visual Studio 성능 향상  
 팁과 요령 큰 솔루션 또는 메모리 부족 상태를 처리할 때 Visual Studio 성능을 향상 하는 방법에 대 한 참조 [큰 솔루션에 대 한 성능 고려 사항](https://github.com/dotnet/roslyn/wiki/Performance-considerations-for-large-solutions)합니다.  
  
## <a name="full-solution-analysis-suspended"></a>전체 솔루션 분석 사용 일시 중단  
 기본적으로 전체 솔루션 분석 사용 Visual basic의 경우 사용 되 고 Visual C#을 사용할 수 없습니다. 그러나 메모리 부족 상태에서 전체 솔루션 분석 사용은 자동으로 비활성화 Visual Basic 및 Visual C#에 대 한 설정에 관계 없이 옵션 대화 상자. 그러나 다시 설정할 수 있습니다 전체 솔루션 분석 사용을 선택 하 여는 **다시 사용 하도록 설정** 것이 표시 되 면 선택 하 여 막대 정보에는 단추는 **전체 솔루션 분석 사용** 여 또는 옵션 대화 상자에서 확인란 Visual Studio를 다시 시작 합니다. 옵션 대화 상자는 항상 현재 전체 솔루션 분석 설정을 표시합니다. 자세한 내용은 참조 [하는 방법: 전체 솔루션 분석 사용 하지 않도록 설정 하며 사용](../code-quality/how-to-enable-and-disable-full-solution-analysis-for-managed-code.md)합니다.  
  
## <a name="gc-low-latency-disabled"></a>GC 낮은 대기 시간 사용 하지 않도록 설정  
 GC 낮은 대기 시간 모드를 다시 활성화 하려면 Visual Studio를 다시 시작 합니다.  기본적으로 Visual Studio 입력 내용을 GC 작업 차단 하지 않는 텍스트를 입력할 때마다 GC 낮은 대기 시간 모드를 사용 합니다. 그러나 메모리가 부족 한 경우 자동 일시 중단 경고를 표시 하려면 Visual Studio, GC 낮은 대기 시간 모드는 해당 세션에 대해 비활성화 됩니다. Visual Studio를 다시 시작 기본 GC 동작에 다시 사용 하도록 설정 됩니다. 자세한 내용은 참조 [GCLatencyMode 열거형](http://msdn.microsoft.com/Library/057757a5-cd62-4d13-8a40-370eb7f47c87)합니다.  
  
## <a name="visual-studio-caches-flushed"></a>Visual Studio 캐시 플러시  
 모든 Visual Studio 캐시를 비우기 즉시 하지만 계속 하려면 현재 개발 세션 또는 Visual Studio를 다시 시작 하는 경우 다시 채우기가 시작 됩니다. 플러시된 캐시는 다음과 같은 기능에 대 한 캐시를 포함 합니다.  
  
-   모든 참조 찾기  
  
-   다음 탐색  
  
-   사용 하 여 추가  
  
 또한 내부 Visual Studio 작업에 사용 되는 캐시도 지워집니다.  
  
> [!NOTE]
>  자동 기능 일시 중단 경고 세션당 기반이 아니라 솔루션 별로 한 번만 발생합니다. 즉, Visual Basic에서 Visual C# (또는 그 반대로)로 전환 하 고 다른 메모리 부족 상태를 실행 하는 경우 확인할 수 있는 가능한 다른 자동 기능 일시 중단 경고 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [방법: 전체 솔루션 분석 활성화 및 비활성화](../code-quality/how-to-enable-and-disable-full-solution-analysis-for-managed-code.md)   
 [가비지 수집 기본 사항](/dotnet/standard/garbage-collection/fundamentals)   
 [대규모 솔루션에 대 한 성능 고려 사항](https://github.com/dotnet/roslyn/wiki/Performance-considerations-for-large-solutions)