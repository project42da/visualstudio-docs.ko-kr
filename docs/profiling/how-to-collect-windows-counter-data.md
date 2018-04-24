---
title: '방법: Windows 카운터 데이터 수집 | Microsoft 문서'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.property.syscounter
- vs.performance.property.wincounter
helpviewer_keywords:
- windows counters
- performance tools, using windows counters
- profiling tools, using windows counters
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 842ce89c687c1f39bc013a7b1eb2c4b330a86f47
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2018
---
# <a name="how-to-collect-windows-counter-data"></a>방법: Windows 카운터 데이터 수집

Windows 카운터는 프로파일링 중에 설정된 간격으로 수집할 수 있는 시스템 성능 카운터입니다. 프로파일링 도구 보고서의 표시 뷰에서 각 수집 간격에 대한 행에는 **AutoMark** 레이블이 지정됩니다. 행에는 해당 간격으로 성능 카운터 값을 설명하는 열이 포함됩니다. 두 개의 특정 표시 간에 경과한 기간으로 분석을 제한하려면 표시를 선택하고, 마우스 오른쪽 단추를 클릭하고 나서, 바로 가기 메뉴에서 **필터링 기준** ->  **표시**를 선택합니다.

> [!NOTE]
> Windows 8 및 Windows Server 2012의 강화된 보안 기능을 위해 Visual Studio 프로파일러가 이러한 플랫폼에서 데이터를 수집하는 방법을 상당히 변경해야 했습니다. 또한 UWP 앱에는 새로운 수집 기술도 필요합니다. [Windows 8 및 Windows Server 2012 응용 프로그램의 성능 도구](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md)를 참조하세요.

## <a name="to-collect-windows-counter-data"></a>Windows 카운터 데이터를 수집하려면

1. [성능 탐색기]에서 Windows 카운터를 구성할 세션을 마우스 오른쪽 단추로 클릭하고 **속성**을 선택합니다.

2. **속성 페이지**에서 **Windows 카운터**를 클릭합니다.

3. **Windows 카운터 수집** 확인란을 선택합니다.

4. **수집 간격(밀리초)** 텍스트 상자에 시간 간격을 입력합니다.

5. **카운터 범주** 드롭다운 목록에서 범주를 선택합니다.

6. **인스턴스** 드롭다운 목록에서 인스턴스를 선택합니다.

7. 응용 프로그램을 프로파일링할 때 사용할 카운터를 선택합니다.

8. **적용**을 클릭합니다.

## <a name="see-also"></a>참고 항목

[성능 세션 구성](../profiling/configuring-performance-sessions.md)  
[성능 세션 속성](../profiling/performance-session-properties.md)  
[CPU 및 Windows 카운터](../profiling/cpu-and-windows-counters.md)