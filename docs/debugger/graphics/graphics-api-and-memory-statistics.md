---
title: "그래픽 API 및 메모리 통계 | Microsoft Docs"
ms.custom: 
ms.date: 03/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.graphics.apistatistics
- vs.graphics.memorystatistics
ms.assetid: 27d2f303-e3ed-4219-9009-345a0d849506
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: c34c505751153410896da66040c866676c3a7ee2
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="graphics-api-and-memory-statistics"></a>그래픽 API 및 메모리 통계
<!-- VERSIONLESS -->
Visual Studio 2017 및 보다 폭넓게 지원 그래픽 API 통계 및 메모리 통계 도구를 제공 합니다.  이 두 가지 도구는 Direct3D API 사용: 다양 한 리소스의 GPU 메모리 소비량에 다양 한 비트의 정보를 볼 수 있습니다.

## <a name="graphics-api-statistics"></a>그래픽 API 통계
Visual Studio 그래픽 진단의 그래픽 API 통계 모든 적용 된 Direct3D 호출 하 고 각 호출의 수를 볼 수 있습니다.  선택 된 창을 보려면는 **보기 > API 통계** 메뉴 항목입니다.

![API 통계](media/gfx_diag_api_statistics.png)

이 도구는 사용자를 인지 하지 못할 수도 DirectX 호출 하는 중, 검색 또는 너무 자주 하는 호출에 유용할 수 있습니다.

모두 복사 데이터 창에서을 마우스 오른쪽 단추로 추가 분석을 위해 다음과 같이 Excel에 붙여 넣을 수 있는 CSV로 수 있습니다.

## <a name="memory-statistics"></a>메모리 통계
이 도구는 프레임에 만들어야 하는 리소스에 대 한 그래픽 드라이버를 할당 중인 메모리 양을 표시 됩니다.  이 창을 표시 하려면 선택은 **보기 > 메모리 통계** 메뉴 항목입니다.

![메모리 통계](media/gfx_diag_memory_statistics.png)

**GPU 할당** 열에 표시 된 이벤트에 의해 사용 된 메모리 양이 표시 됩니다는 **이벤트** 열입니다.  조사식 아이콘을 선택할 수도 있습니다 ![조사식 아이콘](media/gfx_watch.png) 볼 수는 [리소스 기록](graphics-event-list.md#resource-history) 선택한 이벤트에 대 한 합니다.

API 통계 도구와 마찬가지로 추가 분석을 위해 다음과 같이 Excel에 붙여 넣을 수 있는 CSV로 모두 복사 데이터 창에서 단추로 수 있습니다.

## <a name="see-also"></a>참고 항목  
[그래픽 진단 (DirectX 그래픽 디버그)](visual-studio-graphics-diagnostics.md)   
[리소스 기록](graphics-event-list.md#resource-history)
<!-- /VERSIONLESS -->