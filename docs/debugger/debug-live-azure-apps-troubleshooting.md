---
title: 스냅숏 디버깅에 대 한 문제 해결 및 알려진 문제 | Microsoft Docs
ms.date: 11/07/2017
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- debugger
ms.assetid: 511a0697-c68a-4988-9e29-8d0166ca044a
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 7340b5f6ce7e9f8cbcbb0e2673b22712b3ab45a3
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2018
---
# <a name="troubleshooting-and-known-issues-for-snapshot-debugging-in-visual-studio"></a>스냅숏 Visual Studio의 디버깅에 대 한 문제 해결 및 알려진 문제

이 항목에 설명 된 단계 문제를 해결 하지 않을 경우 문의 snaphelp@microsoft.com합니다.

## <a name="issue-snappoint-does-not-turn-on"></a>문제: Snappoint 켜지 지 않음

경고 아이콘이 표시 되 면 ![Snappoint 경고 아이콘이](../debugger/media/snapshot-troubleshooting-snappoint-warning-icon.png "Snappoint 경고 아이콘이") 일반 snappoint 아이콘 대신 프로그램 snappoint,으로 다음의 snappoint 켜져 있지 않습니다.

![Snappoint 켜지 지 않는](../debugger/media/snapshot-troubleshooting-dont-turn-on.png "Snappoint 켜지 지 않음")

이러한 단계를 따릅니다.

1. 소스 코드를 빌드하고 app.isua1 프로그램을 배포 하는 데 사용 된 같은 버전이 있는지 확인 합니다. 올바른 기호를 로드 하는 배포에 있는지 확인 합니다. 이렇게 하려면 보기는 **모듈** 창 스냅숏 디버깅 도중 및 기호 파일 열 표시.pdb 파일을 디버깅 하는 모듈에 대 한 로드를 확인 합니다. Note 스냅숏 디버거가 자동으로 다운로드 하 고 배포에 대 한 기호를 사용 하 여 시도 합니다.

## <a name="issue-symbols-do-not-load-when-i-open-a-snapshot"></a>문제: 스냅숏으로 열 때 기호 로드 하지 않음

창 다음 표시 되 면 기호 로드 되지 않았습니다.

![기호를 로드 하지 않습니다](../debugger/media/snapshot-troubleshooting-symbols-wont-load.png "기호를 로드 하지 않습니다")

이러한 단계를 따릅니다.

- 클릭는 **기호 설정을 변경 중...** 이 페이지에 연결 합니다. 에 **디버깅 > 기호** 설정, 기호 캐시 디렉터리를 추가 합니다. 스냅숏 디버깅 기호 경로 설정 된 후 다시 시작 합니다.

   기호 또는 프로젝트에서 사용할 수 있는.pdb 파일에는 응용 프로그램 서비스 배포를 일치 해야 합니다. 대부분의 배포 (Visual Studio, VSTS 또는 Kudu, CI/CD를 통해 배포 등) 응용 프로그램 서비스에 따라 기호 파일을 게시 합니다. 이러한 기호를 사용 하도록 Visual Studio를 사용 하면 기호 캐시 디렉터리를 설정 합니다.

   ![기호 설정](../debugger/media/snapshot-troubleshooting-symbol-settings.png "기호 설정")

- 또는 조직 기호 서버를 사용 하 여 또는 다른 경로 있는 기호를 삭제 하는 경우 배포에 대 한 올바른 기호를 로드 하려면 기호 설정을 사용 합니다.

## <a name="issue-i-cannot-see-the-attach-snapshot-debugger-option-in-the-cloud-explorer"></a>"스냅샷 디버거 연결" 옵션 클라우드 탐색기에서 볼 수 없는 문제:

이러한 단계를 따릅니다.

- 스냅숏 디버거 구성 요소가 설치 되어 있는지 확인 합니다. Visual Studio 설치 관리자를 열고 확인는 **스냅숏 디버거** Azure 작업의 구성 요소입니다.
- 응용 프로그램 지원 되는지 확인 합니다. 현재만 ASP.NET (4.6.1+) 및 Azure 앱 서비스에 배포 된 ASP.NET Core (2.0 이상) 앱이 지원 됩니다.

## <a name="issue-i-only-see-throttled-snapshots-in-the-diagnostic-tools"></a>문제: 표시 되는 진단 도구에 대 한 스냅숏 제한

![Throttled snappoint](../debugger/media/snapshot-troubleshooting-throttled-snapshots.png "snappoint 제한")

이러한 단계를 따릅니다.

- 스냅숏을 매우 적은 양의 메모리를 사용 하지만, 할당 된 메모리는 필요. 스냅숏 디버거에서 서버는 과도 한 메모리 로드를 발견 하면 스냅숏 미치지 않습니다. 스냅숏 디버거 세션을 중지 하 고 다시 시도 하 여 이미 캡처된 스냅숏을 삭제할 수 있습니다.

## <a name="known-issues"></a>알려진 문제

- 동일한 응용 프로그램 서비스에 대해 여러 Visual Studio 클라이언트를 사용 하 여 스냅숏 디버깅 현재 지원 되지 않습니다.
- Roslyn IL 최적화 ASP.NET Core 프로젝트에서 완전히 지원 되지 않습니다. 일부 ASP.NET Core 프로젝트에 대 한 일부 변수를 보거나 조건문에서 몇 가지 변수를 사용 하려면 못할 수 있습니다. 
- 특별 한 변수와 같은 *$FUNCTION* 또는 *$CALLER*, ASP.NET Core 프로젝트에 대 한 logpoints 또는 조건문에서 계산할 수 없습니다.
- 스냅숏 디버깅 된 응용 프로그램 서비스에서 작동 하지 않을 [로컬 캐싱](/azure/app-service/app-service-local-cache) 켜져 있습니다.
- API 앱을 디버깅 하는 스냅숏 현재 지원 되지 않습니다.

## <a name="site-extension-upgrade"></a>사이트 확장 업그레이드

스냅숏 디버깅 및 Application Insights 사이트 프로세스를 로드 하 고 업그레이드 하는 동안 파일 잠금 문제가 발생 하는 ICorProfiler에 따라 다릅니다. 프로덕션 사이트에 없는 가동 중지 시간이 있도록 하기 위해이 프로세스를 사용 하는 것이 좋습니다.

- 만들기는 [배포 슬롯](/azure/app-service/web-sites-staged-publishing) 응용 프로그램 서비스 내에서 슬롯에 사이트를 배포 합니다.
- Azure 포털에서 나 Visual Studio 클라우드 탐색기에서 프로덕션으로 슬롯의 교환 합니다.
- 슬롯 사이트를 중지 합니다. 모든 인스턴스에서 사이트 w3wp.exe 프로세스를 중지 하려면 몇 초 정도 걸립니다.
- Kudu 사이트 또는 Azure 포털에서 슬롯 사이트 확장을 업그레이드 (*앱 서비스 블레이드 > 개발 도구 > 확장 > 업데이트*).
- 슬롯 사이트를 시작 합니다. 다시 준비 사이트를 방문 하는 것이 좋습니다.
- 프로덕션으로 슬롯의 교환 합니다.

## <a name="see-also"></a>참고자료

[Visual Studio의 디버깅](../debugger/index.md)  
[스냅숏 디버거를 사용 하 여 라이브 ASP.NET 앱 디버그](../debugger/debug-live-azure-applications.md)  
[스냅숏 디버깅 FAQ](../debugger/debug-live-azure-apps-faq.md)  
