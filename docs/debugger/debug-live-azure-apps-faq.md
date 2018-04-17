---
title: 스냅숏 디버깅에 대 한 FAQ | Microsoft Docs
ms.date: 11/07/2017
ms.technology:
- vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- debugger
ms.assetid: 944f1eb0-a74b-4d28-ae2b-a370cd869add
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: db887f783cf205bb7951cde985fa371ab1ab755c
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="frequently-asked-questions-for-snapshot-debugging-in-visual-studio"></a>스냅숏 Visual Studio에서 디버깅에 관한 질문과 대답

다음은 스냅숏 디버거를 사용 하 여 라이브 Azure 응용 프로그램을 디버깅할 때를 수행할 수 있는 질문의 목록입니다.

#### <a name="what-is-the-performance-cost-of-taking-a-snapshot"></a>스냅숏 만들기의 성능 비용은 얼마 입니까?

스냅숏 디버거 응용 프로그램의 스냅숏을 캡처한 응용 프로그램의 프로세스 분기과 분기 복사본을 일시 중단 됩니다. 스냅숏을 디버깅할 때 프로세스의 분기 복사본에 대해 디버깅 하는 합니다. 이 프로세스 10-20 밀리초 동안만 걸리지만 응용 프로그램의 전체 힙 복사 하지 않습니다. 대신,만 페이지 테이블을 복사 하 고 페이지를 기록 중 복사를 설정 합니다. 일부 응용 프로그램의 개체 힙 변경 시 해당 페이지의 복사 됩니다. 따라서 각 스냅숏은 (대부분의 응용 프로그램 (킬로바이트) 수백)의 순서는 매우 작은 메모리에 비용을 포함 됩니다. 

#### <a name="what-happens-if-i-have-a-scaled-out-azure-app-service-multiple-instances-of-my-app"></a>확장 된 Azure 앱 서비스 (이 응용 프로그램의 여러 인스턴스)이 있는 경우 어떻게 되나요?

응용 프로그램의 여러 인스턴스가 있는 경우 snappoints 모든 단일 인스턴스에 적용 됩니다. 지정 된 조건을 사용 하 여 적중를 첫 번째 snappoint만 스냅숏을 만듭니다. 여러 snappoints를 설정한 경우 후속 스냅숏 첫 번째 스냅숏을 만든 동일한 인스턴스에서 제공 됩니다. 출력 창에 보내는 Logpoints 응용 프로그램 로그로 전송 logpoints 인스턴스마다에서 메시지를 전송 하는 동안 한 인스턴스에서 메시지 표시 됩니다. 

#### <a name="how-does-the-snapshot-debugger-load-symbols"></a>스냅숏 디버거 기호를 로드 하는 방법

스냅숏 디버거는 일치 하는 기호 응용 프로그램에 대 한 하거나 로컬로 했거나 (포함 된 Pdb는 현재 지원 되지 않음) 하 여 Azure 응용 프로그램 서비스에 배포 해야 합니다. 스냅숏 디버거는 자동으로 Azure 앱 서비스에서 기호를 다운로드합니다. Azure 앱 서비스에도 배포 되는 버전 15.2, Visual Studio 2017을 기준으로 앱의 기호를 배포 합니다.

#### <a name="does-the-snapshot-debugger-work-against-release-builds-of-my-application"></a>내 응용 프로그램의 릴리스 빌드에 대해 스냅숏 디버거 작동 합니까?

예-스냅숏 디버거 릴리스 빌드에 대해 작동 하는 데 사용 됩니다. 함수에는 snappoint 넣으면 함수 디버깅 가능 하기는 디버그 버전에 다시 컴파일됩니다. 스냅숏 디버거를 중지 하는 경우 해당 릴리스 빌드를 함수 반환 됩니다. 

#### <a name="can-logpoints-cause-side-effects-in-my-production-application"></a>Logpoints는 프로덕션 응용 프로그램에서 부작용이 발생 수 있습니까?

아니요-앱에 추가 된 로그 메시지는 사실상 평가 됩니다. 응용 프로그램에서 의도 하지 않은 모든 소멸자 수 없습니다. 그러나 일부 네이티브 속성 logpoints로 액세스할 수 있는 수 있습니다. 

#### <a name="does-the-snapshot-debugger-work-if-my-server-is-under-load"></a>내 서버 부하의 경우 스냅숏 디버거 작동 합니까?

예, 부하 상태에서 서버에 대 한 스냅숏 디버깅 작업할 수 있습니다. 스냅숏 디버거 스로틀 및 경우에는 스냅숏을 캡처하지 않습니다는 서버에서 사용 가능한 메모리의 낮은 금액입니다.

#### <a name="how-do-i-uninstall-the-snapshot-debugger"></a>스냅숏 디버거를 제거 하려면 어떻게 해야 합니까?

다음 단계를 사용 하 여 응용 프로그램 서비스에서 스냅숏 디버거 사이트 확장을 제거할 수 있습니다.

1. 응용 프로그램 서비스 해제 Visual Studio 또는 Azure 포털에서 클라우드 탐색기를 통해 합니다.
1. 앱 서비스의 Kudu 사이트로 이동 (즉, yourappservice. **scm**. azurewebsites.net)로 이동 하 고 **확장 사이트**합니다.
1. 제거 하려면 스냅숏 디버거 사이트 확장에 있는 X를 클릭 합니다.

## <a name="see-also"></a>참고자료

[Visual Studio의 디버깅](../debugger/index.md)  
[스냅숏 디버거를 사용 하 여 라이브 ASP.NET 앱 디버그](../debugger/debug-live-azure-applications.md)  
[스냅숏 디버깅에 대 한 문제 해결 및 알려진 문제](../debugger/debug-live-azure-apps-troubleshooting.md)
