---
title: "Office 추가 기능 COM, VSTO 및 VBA에 대 한 개발 모범 사례 | Microsoft Docs"
ms.custom: 
ms.date: 07/25/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: 
helpviewer_keywords: 
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 2a1b6b9270207b3d0f8d415655231af4456e61b4
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/10/2018
---
# <a name="development-best-practices-for-com-vsto-and-vba--add-ins-in-office"></a>Office에서 COM, VSTO 및 VBA 추가 기능에 대 한 개발 모범 사례
  Office에 대 한 COM 이거나 VBA VSTO 추가 기능을 개발 하는 경우에이 문서에 설명 된 개발 모범 사례를 준수 합니다.   이렇게 하면 확인 하는 데 도움이 됩니다.

-  추가 기능이 다른 버전 및 Office의 배포에서의 호환 됩니다.
-  사용자 및 IT 관리자에 대 한 추가 기능을 배포의 복잡성이 감소 합니다.
-  추가 기능에서 의도 하지 않은 설치 또는 런타임 오류가 발생 하지 않습니다.

>참고:를 사용 하 여 [데스크톱 브리지](/windows/uwp/porting/desktop-to-uwp-root) 사용자 COM를 준비 하려면 VBA 또는 VSTO 추가 기능을 Windows 스토어는 지원 되지 않습니다. Office 스토어 또는 Windows 스토어에서 COM, VSTO 및 VBA 추가 기능을 배포할 수 없습니다. 
  
## <a name="do-not-check-for-office-during-installation"></a>설치 하는 동안 Office에 대 한 검사 안 함  
 Office 추가 기능 설치 프로세스 중 설치 여부 검색 추가 기능에 필요 하지 않는 것이 좋습니다. Office 설치 되어 있지 않으면에서 추가 기능을 설치할 수 있습니다 및 사용자는 Office가 설치 된 후에 액세스할 수 있습니다. 
  
## <a name="use-embedded-interop-types-nopia"></a>포함 된 Interop 형식 (NoPIA)를 사용 하 여  
솔루션.NET 4.0을 사용 하거나 나중에 사용 하는 경우 포함 된 interop 형식 (NoPIA) 대신에 따라는 Office 주 Interop 어셈블리 (PIA) 재배포 가능 합니다. 포함 하는 형식을 사용 하 여 솔루션의 설치 크기를 줄이는 및 이후 버전과 호환성을 보장 합니다. Office 2010의 Office PIA 재배포 가능 패키지를 함께 제공 되는 마지막 버전 이었습니다. 자세한 내용은 참조 [연습: Microsoft Office 어셈블리의 형식 정보 포함](https://msdn.microsoft.com/en-us/library/ee317478.aspx) 및 [동일 형식 및 포함 된 Interop 형식](/windows/uwp/porting/desktop-to-uwp-root)합니다.

솔루션에는 이전 버전의.NET을 사용 하는 경우.NET 4.0 이상을 사용 하 여 솔루션을 업데이트 하는 것이 좋습니다. .NET 4.0 이상을 사용 하 여 최신 버전의 Windows에 런타임 필수 구성 요소를 줄입니다.
  
## <a name="avoid-depending-on-specific-office-versions"></a>특정 Office 버전에 따라 방지  
솔루션만 최신 버전의 Office에서 사용할 수 있는 기능을 사용 합니다 (예: 예외 처리 또는 버전을 확인 하 여 사용 하 여) 런타임 시 기능 (가능한 경우 기능 수준)에서 있는지을 확인 합니다. 개체 모델을와 같은 지원 되는 Api를 사용 하 여 특정 버전 보다는 최소 버전의 유효성을 검사는 [Application.Version 속성](https://msdn.microsoft.com/en-us/library/office/microsoft.office.interop.excel._application.version.aspx)합니다. 이러한 설치, 환경 및 버전 간에 변경 될 수 있으므로 Office 이진 메타 데이터, 설치 경로 또는 레지스트리 키에 의존 하지 않는 것이 좋습니다.

## <a name="enable-both-32-bit-and-64-bit-office-usage"></a>32 비트 및 64 비트 Office 사용 사용 하도록 설정   
솔루션에만 특정 비트 수에 사용할 수 있는 라이브러리에 의존 하지 않는 한 기본 build 대상을 (x86) 32 비트 및 64 비트 (x64) 모두 지원 해야 합니다. 64 비트 버전 Office의 채택 특히 빅 데이터 환경에서에서 계속 증가 하는 합니다. 32 비트 및 64 비트 지원 쉽게 사용자가 32 비트 및 64 비트 버전의 Office 사이 전환 합니다.

VBA 코드를 작성할 때 사용 하 여 64 비트 safe는 declare 문 및 변수를 적절 하 게를 변환 합니다. 또한 문서 각 비트에 대 한 코드를 제공 하 여 32 비트 또는 64 비트 버전의 Office 실행 하는 사용자 간에 공유할 수 있는지 확인 합니다. 자세한 내용은 참조 [64 비트 Visual Basic 응용 프로그램 개요](https://msdn.microsoft.com/en-us/library/office/gg264421.aspx)합니다.

## <a name="support-restricted-environments"></a>제한 된 환경 지원   
솔루션에는 사용자 계정 상승 또는 관리자 권한이 필요 하지 않습니다. 또한 솔루션 설정 또는 변경에 의존 하지 해야 합니다.

- 현재 작업 디렉터리입니다.
- DLL이 로드 디렉터리입니다.
- 경로 변수입니다.

## <a name="change-the-save-location-of-shared-data-and-settings"></a>변경 데이터를 공유 및 설정의 위치
솔루션으로 구성 된 경우 추가 기능 및 프로세스 외부에 Office를 사용 하지 마십시오 사용자의 응용 프로그램 데이터 폴더 또는 레지스트리를 데이터 또는 설정을 추가 및 외부 프로세스 간에 교환. 대신, 사용자의 임시 폴더, 문서 폴더 또는 솔루션의 설치 디렉터리를 사용 하는 것이 좋습니다.

## <a name="increment-the-version-number-with-each-update"></a>업데이트할 때마다 버전 번호를 하나씩 늘립니다.
솔루션에 이진 파일의 버전 번호를 설정 하 고 각 업데이트를 하나씩 늘립니다. 이것은 쉽게 버전 간의 변경 내용을 식별 하 고 호환성을 평가 하는 사용자에 대 한 있습니다.

## <a name="provide-support-statements-for-the-latest-versions-of-office"></a>최신 버전의 Office에 대 한 지원 설명을 제공 합니다.
고객은 자신의 COM, VSTO 및 VBA 추가 기능은 Office에서 실행에 대 한 지원 설명을 제공 하는 Isv 요청할 수도 있습니다. Office 365 ProPlus를 사용 하 여 명시적으로 지원 문을 사용 하면 고객이 나열 준비 도구는 사용자를 지 원하는 이해 합니다. 

Office 클라이언트 응용 프로그램 (예를 들어 Word 또는 Excel)에 대 한 지원 정보와 제공 하려면 먼저 추가 기능이 현재 Office 버전에서 실행 및 커밋의 이후 릴리스에서 중단에 추가 되 면 업데이트를 제공 하는 것을 확인 합니다. Microsoft Office에 대 한 업데이트 또는 새 빌드를 놓을 때 추가 기능을 테스트할 필요가 없습니다. Microsoft office에서는 COM, VSTO 및 VBA 확장성 플랫폼을 거의 변경 되 고 이러한 변경 내용을 잘 문서화 됩니다.

>중요: Microsoft 준비 보고서 및 ISV 연락처 정보에 대 한 지원 되는 추가 기능 목록을 유지 관리 합니다. 참조 추가 기능에 나열 된 가져오려는 [https://aka.ms/readyforwindows](https://aka.ms/readyforwindows)합니다.

## <a name="use-process-monitor-to-help-debug-installation-or-loading-issues"></a>프로세스 모니터를 사용 하 여 설치 또는 로드 하는 문제를 디버깅 하는 데
추가 기능을 설치 또는 로드 하는 동안에 호환성 문제가, 파일 또는 레지스트리 액세스 문제를 관련 수 있습니다. 사용 하 여 [프로세스 모니터](/sysinternals/downloads/procmon) 또는 유사한 디버깅 도구 로그인 하 여 문제를 식별할 수 있도록 작업 환경에 대 한 동작을 비교 합니다.
