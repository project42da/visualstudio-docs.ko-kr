---
title: Visual Studio에서 부하 테스트에 대한 데이터 및 진단 첨부 파일 보기 | Microsoft Docs
ms.date: 10/19/2016
ms.topic: article
helpviewer_keywords:
- load tests, data and diagnostics attachments
ms.assetid: 73309bdd-437a-4eb0-88c8-702c3e24b9b0
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-ide-test
ms.openlocfilehash: 5d955412195a32a69e069ccac2b40456a9ffb986
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2018
---
# <a name="how-to-view-data-and-diagnostic-attachments-using-the-load-test-analyzer"></a>방법: 부하 테스트 분석기를 사용하여 데이터 및 진단 첨부 파일 보기

부하 테스트를 실행하기 전에 사용할 진단 데이터 어댑터를 지정하는 테스트 설정을 선택할 수 있습니다. 부하 테스트를 마친 후 부하 테스트 분석기를 사용하여 결과를 분석하는 동안 이러한 진단 데이터 어댑터에 대한 정보를 볼 수 있습니다. 진단 데이터 어댑터 정보를 보려면 부하 테스트 분석기의 도구 모음에서 **데이터 및 진단 첨부 파일 보기** 단추를 선택합니다. 예를 들어 부하 테스트 시 테스트 설정에 시스템 정보 어댑터가 구성되어 있던 경우 부하 테스트를 실행할 때 사용된 컴퓨터의 시스템 정보를 볼 수 있습니다.

![진단 데이터 어댑터 첨부 파일 선택 대화 상자](../test/media/load_adapterdialog.png "Load_AdapterDialog")

또 다른 예로, 부하 테스트의 테스트 설정에 IntelliTrace 어댑터가 포함되어 있으면 IntelliTrace 어댑터를 사용하여 IntelliTrace 요약 페이지를 열 수 있습니다.

![IntelliTrace 요약](../test/media/load_intellitrace.png "Load_IntelliTrace")

자세한 내용은 [테스트 설정을 사용하여 진단 정보 수집](../test/collect-diagnostic-information-using-test-settings.md) 및 [IntelliTrace 데이터 수집](../test/how-to-collect-intellitrace-data-to-help-debug-difficult-issues.md)을 참조하세요.

## <a name="to-view-data-and-diagnostic-attachments-in-a-load-test-from-the-load-test-analyzer"></a>부하 테스트 분석기에서 부하 테스트의 데이터 및 진단 첨부 파일을 보려면

1.  부하 테스트가 완료된 후 또는 부하 테스트 결과를 연 후 부하 테스트 분석기의 도구 모음에서 **데이터 및 진단 첨부 파일 보기**를 선택합니다.

     **진단 데이터 어댑터 첨부 파일 선택** 대화 상자가 표시됩니다.

2.  분석할 진단 데이터 어댑터 첨부 파일을 선택하고 **확인**을 선택합니다.

## <a name="see-also"></a>참고 항목

- [부하 테스트 결과 분석](../test/analyze-load-test-results-using-the-load-test-analyzer.md)