---
title: Visual Studio가 느린 경우 성능 향상
ms.date: 04/11/2018
ms.topic: conceptual
helpviewer_keywords:
- performance [Visual Studio]
author: gewarren
ms.author: gewarren
manager: douge
f1_keywords:
- vs.performancecenter
ms.technology: vs-ide-general
ms.workload:
- multiple
ms.openlocfilehash: 0ce1f0e8b7ab522cf9272918a794d61e09cd243d
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="optimize-visual-studio-performance"></a>Visual Studio 성능 최적화

이 문서에서는 Visual Studio 느리게 실행되는 경우 몇 가지 시도해볼 제안을 제공합니다. 성능 향상 방법에 대한 더 많은 제안은 [Visual Studio 성능 팁 및 요령](../ide/visual-studio-performance-tips-and-tricks.md)을 참조할 수 있습니다.

## <a name="upgrade-to-visual-studio-2017-version-156-or-later"></a>Visual Studio 2017 버전 15.6 이상으로 업그레이드

현재 Visual Studio 2015를 사용하는 경우 무료로 [Visual Studio 2017](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)을 다운로드하여 향상된 성능을 확인해보십시오. 솔루션은 다른 영역에서도 성능 향상으로 Visual Studio 2017에서 2-3배 더 빠르게 로드합니다. Visual Studio 2017은 Visual Studio 2015와 호환가능하므로 2017을 사용해도 어떤 손실도 없습니다.

현재 Visual Studio 2017을 사용 중인 경우 버전 15.6 이상을 실행하고 있는지 확인합니다. 데이터에 따르면 버전 15.6에서 솔루션이 최대 2-3배 더 빠르게 로드됩니다. [여기서](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs) 다운로드하세요.

## <a name="extensions-and-tool-windows"></a>확장명 및 도구 창

확장명이 설치되어 있으면 Visual Studio가 느려질 수 있습니다. 성능 향상을 위한 확장명 관리에 대한 도움말은 [성능 향상을 위한 확장명 설정 변경](../ide/optimize-visual-studio-startup-time.md#extensions)을 참조합니다.

마찬가지로 도구창이 있으면 Visual Studio가 느려질 수 있습니다. 도구 창 관리에 관한 도움말은 [성능 향상을 위한 도구 창 설정 변경](../ide/optimize-visual-studio-startup-time.md#tool-windows)을 참조합니다.

## <a name="hardware"></a>하드웨어

하드웨어 업그레이드를 고려하는 경우 RAM 추가나 더 빠른 CPU 장착보다 SSD(side-by-side)가 성능에는 더 큰 영향을 미칩니다.

최적의 성능을 위해 SSD를 추가하는 경우 HDD(hard disk drive)에 대조적으로 해당 드라이브에 Windows를 설치합니다. Visual Studio 솔루션의 드라이브 위치는 별로 중요하지 않은 것 같습니다.

또한 USB 드라이브에서 솔루션을 실행하지 마십시오. 솔루션을 HDD 또는 SSD에 복사합니다.

## <a name="help-us-improve"></a>개선할 수 있도록 도와주세요

여러분의 의견이 개선에 도움이 됩니다. **문제 보고** 기능을 사용하여 추적을 "레코드"하고 당사에 보내십시오. **빠른 실행** 옆에 있는 피드백 아이콘을 선택하거나 메뉴 모음에서 **도움말** > **의견 보내기** > **문제 보고**를 선택합니다. 자세한 내용은 [Visual Studio 2017의 문제를 보고하는 방법](../ide/how-to-report-a-problem-with-visual-studio-2017.md)을 참조하세요.

## <a name="see-also"></a>참고 항목

- [성능 팁 및 요령](../ide/visual-studio-performance-tips-and-tricks.md)
- [Visual Studio 블로그 - Visual Studio 2017 버전 15.6으로 더 빠르게 솔루션 로드](https://blogs.msdn.microsoft.com/visualstudio/2018/04/04/load-solutions-faster-with-visual-studio-2017-version-15-6/)
