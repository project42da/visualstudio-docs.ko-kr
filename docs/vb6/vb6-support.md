---
title: "Visual Basic 6.0에 대 한 지원 정책 | Microsoft Docs"
ms.date: 08/28/2017
ms.technology: devlang-vb
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- VB6 support
- Visual Basic 6.0 support
ms.assetid: ffc5ba4d-44d7-4ef7-a3f6-38a8738bf127
author: paulyuk
ms.author: paulyuk
ms.workload:
- paulyuk
ms.openlocfilehash: cb25f85be6c77dfbef6969435d14f2cae61debf2
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2018
---
# <a name="support-statement-for-visual-basic-60-on-windows"></a>Visual Basic 6.0에서 Windows에 대 한 지원 정책


## <a name="executive-summary"></a>실행 요약

Visual Basic 팀은 다음과 같은 지원 되는 Windows 운영 체제에서 Visual Basic 6.0 응용 프로그램에 대 한 "만 작동" 호환성 위해 노력 합니다. 

- Windows 10
- Windows 8.1
- Windows 7
- Windows Server 2016
- Windows Server 2012 r 2를 포함 합니다.
- Windows Server 2008 r 2를 포함 하 여

Visual Basic 팀의 목표는 Visual Basic 6.0 응용 프로그램에서 계속 실행 지원 되는 Windows 버전입니다. 단계에서 설명한 대로이 문서를 Visual Basic 6.0 핵심 런타임을 지원 됩니다 지원 되는 Windows 버전의 전체 수명 동안 변수인 5 년간의 기본 지원의 확장된 지원 (http://support.microsoft.com/gp/lifepolicy) 5 년이 옵니다. 지원 모음 기존 응용 프로그램에 대 한 중요 한 보안 문제 및 심각한 재발으로 제한 됩니다.

## <a name="technical-summary"></a>기술 요약

Visual Basic 6.0은 이러한 주요 결과물 구성 됩니다.
- Visual Basic 6.0 IDE (통합된 개발 환경)입니다.
- Visual Basic 6.0 런타임: 기본 라이브러리와 실행 엔진 VB 6.0 응용 프로그램을 실행 하는 데 사용 합니다.
- Visual Basic 6.0 런타임 확장 파일: 선택한 ActiveX 컨트롤 OCX 파일, 라이브러리 및 도구는 IDE 미디어 및 온라인 릴리스 다른 이름으로 전달 합니다.

## <a name="the-visual-basic-60-ide"></a>Visual Basic 6.0 IDE

Visual Basic 6.0 IDE는 2008 년 4 월 8 일을 기준으로 더 이상 지원 됩니다. 또한 Windows 및 Visual Basic 팀 Visual Basic 6.0 IDE에서 Windows Vista, Windows 7, Windows Server 2008, Windows 8 및 Windows 8.1 이해 하 고 (필요한 경우)을 완화를 테스트 한 32 비트 버전의 Windows (참조에서 호환성 문제 [64 비트 Windows](#62-bit-windows) 64 비트 시스템에 대 한 자세한 내용은 아래 섹션). 이 알림은 IDE에 대 한 지원 정책을 변경 되지 않습니다.

## <a name="the-visual-basic-60-runtime"></a>Visual Basic 6.0 런타임

Visual Basic 6.0 런타임 Visual Basic 6.0에 대 한 재배포 목록에 포함 된 원래 컴파일된 이진 파일에 정의 되어 있습니다. 이러한 파일은 원래 Visual Basic 6.0 라이선스의 배포 가능으로 표시 되었습니다. 이러한 파일의 예로 Visual Basic 6.0 런타임 라이브러리 (`msvbvm60.dll`), 컨트롤 (즉, `msflxgrd.ocx`) 런타임 함께 다른 주요 기능 영역 (예: MDAC)에 대 한 파일을 지원 합니다.

런타임에서 3 개의 그룹으로 구분 됩니다.

- 지원 되는 런타임 파일-OS에 전달 합니다.

   대부분의 응용 프로그램 시나리오에 사용 된 키 Visual Basic 6.0 런타임 파일에 제공 및 지원 되는 Windows 버전의 수명에 대 한 지원. 수명은 5 년간의 기본 지원 및 지정된 된 버전의 Windows에 제공 되는 시점부터 지원 연장이 5 년입니다. 이러한 파일의 지원 되는 Windows 버전에서 실행 되는 Visual Basic 6.0 응용 프로그램에이 테스트의 일환으로 호환성을 위해 테스트 되었습니다. 

   > [!NOTE]
   > 지원 되는 모든 Windows 버전의 파일을 거의 동일한 목록을 포함 하 고 이러한 파일을 포함 하는 응용 프로그램의 redist 요구 거의 동일 해야 합니다. 한 가지 주요 차이점은 `TriEdit.dll` Windows Vista 이상 버전에서 제거 되었습니다.

- 지원 되는 런타임 파일 –-확장 응용 프로그램과 함께 배포할 파일

   이 확장된 목록은 주요 제어, 라이브러리 및 IDE 미디어 또는 Microsoft.com 개발자 컴퓨터에 설치 된 도구는 구성 됩니다. 일반적으로 VB6 IDE 이러한 컨트롤 개발자 컴퓨터에 기본적으로 설치 합니다. 개발자는 여전히 응용 프로그램을 사용 하 여 이러한 파일을 재배포 해야 합니다. 파일의 지원 되는 버전은 사용할 수 있는 온라인 Microsoft 다운로드 센터 (http://go.microsoft.com/fwlink/?LinkID=142927) 합니다.

- 지원 되지 않는 런타임 파일

   하나 이상의 기본 외부로 이동 있는 일부 파일을 지원 또는 런타임 재배포 가능 패키지의 일부로 포함 하지 않은 (예:에 포함 된는 `\Tools` 레거시 VB4/VB5 응용 프로그램을 지원 하기 위해 IDE 미디어 폴더 또는 타사 컨트롤 것). 이러한 파일은 Windows;에서 지원 되지 않습니다. 대신 이러한 어떤 지원 계약 적용과 함께 제공 된 미디어에 적용 됩니다. 즉, 지원 및 서비스 주위 보증도 하지 않습니다. 어떤 경우에 이러한 라이브러리의 이후 버전은 지원 됩니다. 마이그레이션에 지원 되는 버전 또는 이전 버전과 호환성에 대 한 내용은 아래에 나와 있습니다.

특정 각 지원 그룹에 포함 된 파일 참조는 [런타임 정의](#runtime-definition) 아래 섹션.

## <a name="the-visual-basic-60-support-lifetime"></a>Visual Basic 6.0 지원 수명

지원 및/또는 Visual Basic 6.0 런타임 이진 파일을 전달 지원 되는 Windows 버전에 변경 되지 않습니다 지원 정책 Visual Basic 6.0 IDE 또는 Visual Studio 6.0 IDE에 대 한 전체. 이러한 제품에서 2008 년 4 월 8 일에 대 한 추가 지원 벗어납니다.

Microsoft 제품 지원 기간에 대 한 내용은 http://support.microsoft.com/gp/lifepolicy에서 찾을 수 있습니다. 이 지원 수명 주기의 일부로 Microsoft는 이러한 운영 체제의 지원 수명에 대 한 Visual Basic 6.0 런타임 지원 되는 Windows 버전에서 지 원하는 데 계속 합니다. 즉, 예를 들어 2008 년 6 월에 대 한 기본 지원 및 확장 지원에 대 한 2013 년 6 월 일 까지만 Visual Basic 6.0 런타임은 Windows Server 2003에서 지원 됩니다 됩니다.
자세한 내용은 지원 수명 주기 또는 추가 지원 옵션에 자세히 알아보려면 http://www.microsoft.com/support에 지원 페이지를 방문 하십시오.

## <a name="64-bit-windows"></a>64 비트 Windows

Visual Basic 6.0 런타임 파일은 32 비트입니다. 이러한 파일에 64 비트 Windows 운영 체제에서 아래 표 참조를 제공 합니다. 32 비트 VB6 응용 프로그램 및 구성 요소는 WOW 에뮬레이션 환경에서 지원 됩니다. 또한 32 비트 구성 요소를 32 비트 응용 프로그램 프로세스에서 호스팅되어야 합니다.

Visual Basic 6.0 IDE에서 네이티브 64 비트 버전에서 제공 하지도 64 비트 Windows에서 32 비트 IDE 지원 되었습니다. Windows 64 비트 또는 32 비트 이외의 모든 네이티브 아키텍처에서 VB6 개발 하지 않으며 지원 되지 않습니다.

## <a name="windows-7"></a>Windows 7

이 지원 설명은의 초기 릴리스 이후 Windows 7 운영 체제 릴리스 되었습니다. 이 문서 VB6 Windows 7에 대 한 Microsoft 지원은 명시 하도록 업데이트 되었습니다.

VB6 런타임 배송 됩니다 및 운영 체제의 수명에 대 한 Windows 7에서 지원 됩니다. Visual Basic 6.0 런타임 파일 계속만 32 비트 여야 하 고 모든 구성 요소는 32 비트 응용 프로그램 프로세스에서 호스트 되어야 합니다.

## <a name="windows-81"></a>Windows 8.1

이 지원 설명은의 초기 릴리스 이후 Windows 8.1 운영 체제 릴리스 되었습니다. 이 문서 VB6 Windows 8.1 대 한 Microsoft 지원은 명시 하도록 업데이트 되었습니다.

VB6 런타임 배송 됩니다 및 운영 체제의 수명에 대 한 Windows 8.1 지원 됩니다. Visual Basic 6.0 런타임 파일 계속만 32 비트 여야 하 고 모든 구성 요소는 32 비트 응용 프로그램 프로세스에서 호스트 되어야 합니다. 개발자는 Windows 7의 경우와 동일한 것으로 Windows 8.1 대 한 지원 스토리의 생각할 수 있습니다.

## <a name="windows-10"></a>Windows 10

이 지원 설명은의 초기 릴리스 이후 Windows 10 운영 체제 릴리스 되었습니다. 이 문서 VB6 Windows 10에 대 한 Microsoft 지원은 명시 하도록 업데이트 되었습니다.

VB6 런타임 배송 됩니다 및 운영 체제의 수명에 대 한 Windows 10에서 지원 됩니다. Visual Basic 6.0 런타임 파일 계속만 32 비트 여야 하 고 모든 구성 요소는 32 비트 응용 프로그램 프로세스에서 호스트 되어야 합니다. 개발자는 Windows 8.1 경우와 동일한 것으로 Windows 10에 대 한 지원 스토리의 생각할 수 있습니다.

## <a name="windows-server-2008"></a>Windows Server 2008

이 지원 설명은의 초기 릴리스 이후 Windows Server 2008 운영 체제 릴리스 되었습니다. 이 문서 VB6 Windows Server 2008에 대 한 Microsoft 지원은 명시 하도록 업데이트 되었습니다.

VB6 런타임 배송 됩니다 및 운영 체제의 수명에 대 한 Windows Server 2008에서 지원 됩니다. Visual Basic 6.0 런타임 파일 계속만 32 비트 여야 하 고 모든 구성 요소는 32 비트 응용 프로그램 프로세스에서 호스트 되어야 합니다.

## <a name="windows-server-2008-r2"></a>Windows Server 2008 R2

이 지원 설명은의 초기 릴리스 이후 Windows Server 2008 R2 운영 체제 릴리스 되었습니다. 이 문서 VB6 Windows Server 2008 r 2에 대 한 Microsoft 지원은 명시 하도록 업데이트 되었습니다.

VB6 런타임 배송 됩니다 및 운영 체제의 수명에 대 한 Windows Server 2008 r 2에서 지원 됩니다. Visual Basic 6.0 런타임 파일 계속만 32 비트 여야 하 고 모든 구성 요소는 32 비트 응용 프로그램 프로세스에서 호스트 되어야 합니다. 개발자는 Windows Server 2008의 경우와 동일한 것으로 Windows Server 2008 r 2에 대 한 지원 스토리의 생각할 수 있습니다.

## <a name="windows-server-2012"></a>Windows Server 2012

이 지원 설명은의 초기 릴리스 이후 Windows Server 2012 운영 체제 릴리스 되었습니다. 이 문서 VB6 Windows Server 2012에 대 한 Microsoft 지원은 명시 하도록 업데이트 되었습니다.

VB6 런타임 배송 됩니다 및 운영 체제의 수명에 대 한 Windows Server 2012에서 지원 됩니다. Visual Basic 6.0 런타임 파일 계속만 32 비트 여야 하 고 모든 구성 요소는 32 비트 응용 프로그램 프로세스에서 호스트 되어야 합니다. 개발자는 Windows Server 2008 r 2의 경우와 동일한 것으로 Windows Server 2012에 대 한 지원 스토리의 생각할 수 있습니다.

## <a name="windows-server-2012-r2"></a>Windows Server 2012 R2

이 지원 설명은의 초기 릴리스 이후 Windows Server 2012 R2 운영 체제 릴리스 되었습니다. 이 문서 VB6 Windows Server 2012 r 2에 대 한 Microsoft 지원은 명시 하도록 업데이트 되었습니다.

VB6 런타임 배송 됩니다 및 운영 체제의 수명에 대 한 Windows Server 2012 r 2에서 지원 됩니다. Visual Basic 6.0 런타임 파일 계속만 32 비트 여야 하 고 모든 구성 요소는 32 비트 응용 프로그램 프로세스에서 호스트 되어야 합니다. 개발자는 Windows Server 2012의 경우와 동일한 것으로 Windows Server 2012 r 2에 대 한 지원 스토리의 생각할 수 있습니다.

## <a name="windows-server-2016"></a>Windows Server 2016

이 지원 설명은의 초기 릴리스 이후 Windows Server 2016 운영 체제 릴리스 되었습니다. 이 문서 VB6 Windows Server 2016에 대 한 Microsoft 지원은 명시 하도록 업데이트 되었습니다.

VB6 런타임 배송 됩니다 및 운영 체제의 수명에 대 한 Windows Server 2016에서 지원 됩니다. Visual Basic 6.0 런타임 파일 계속만 32 비트 여야 하 고 모든 구성 요소는 32 비트 응용 프로그램 프로세스에서 호스트 되어야 합니다. 개발자는 Windows Server 2012 r 2의 경우와 동일한 것으로 Windows Server 2016에 대 한 지원 스토리의 생각할 수 있습니다.

## <a name="supported-windows-operating-system-versions"></a>지원 되는 Windows 운영 체제 버전

이 섹션에서는 일정 수준의 VB6에 대 한 지원 제공 하는 운영 체제에 대 한 추가 정보를 제공 합니다. 

|Windows 운영 체제|지원 되는 런타임 VB6</br>Windows의 파일 지원 있습니까?|VB6 Rutime 지원</br>확장 파일</br>응용 프로그램과 함께 배포 하는 지원?| VB6 IDE에서 지원?|
|---|---|---|---|
|Windows 10에서 모든 32 비트 버전|예 *|예 *|아니요|
|Windows 10에서 모든 64 비트 버전 (WOW에만 해당)|예 * </br> 만 WOW에서 실행 되는 32 비트 응용 프로그램|예* </br> 만 WOW에서 실행 되는 32 비트 응용 프로그램|아니요|
|Windows 8.1, 모든 32 비트 버전|예 *|예 *|아니요|
| Windows 8.1, 모든 64 비트 버전 (WOW에만 해당)|예 * </br> 만 WOW에서 실행 되는 32 비트 응용 프로그램|예* </br> 만 WOW에서 실행 되는 32 비트 응용 프로그램|아니요|
|Windows 7, 모든 32 비트 버전|예 *|예 *|아니요|
|Windows 7, 모든 64 비트 버전 (WOW에만 해당)|예 * </br> 만 WOW에서 실행 되는 32 비트 응용 프로그램|예 * </br> 만 WOW에서 실행 되는 32 비트 응용 프로그램|아니요|
|Windows Server 2016, 모든 64 비트 버전 (WOW에만 해당)|예* </br> 만 WOW에서 실행 되는 32 비트 응용 프로그램|예* </br> 만 WOW에서 실행 되는 32 비트 응용 프로그램|아니요|
|Windows Server 2012 R2, 모든 64 비트 버전 (WOW에만 해당)<br>Windows Server 2012에서 모든 64 비트 버전 (WOW에만 해당)|예* </br> 만 WOW에서 실행 되는 32 비트 응용 프로그램|예* </br> 만 WOW에서 실행 되는 32 비트 응용 프로그램|아니요|
|모든 x64 Windows Server 2008 R2 버전 (WOW에만 해당)</br>모든 x64 Windows Server 2008 버전 (WOW에만 해당)|예 * </br> 만 WOW에서 실행 되는 32 비트 응용 프로그램|예 * </br> 만 WOW에서 실행 되는 32 비트 응용 프로그램|아니요|
|Windows Server 2008에서는 모든 32 비트 버전|예 *|예 *|아니요|


> [!NOTE]
> &#42;  VB6 런타임에서 지원 되는 Windows 지원 기간으로 제한 됩니다.  예를 들어 대상 OS 지원이 연장 이면 VB6 지원이 연장 보다 더 높은 수준의 지원 가질 수 없습니다.  [창은 지원 수명 주기 팩트 시트](https://support.microsoft.com/en-us/help/13853/windows-lifecycle-fact-sheet) 이전 및 현재 Windows 버전에 대 한 수명 주기 추가 정보를 포함 합니다.

## <a name="visual-basic-60-runtime-usage-inside-vba-and-office"></a>VBA 및 Office Visual Basic 6.0 런타임 사용

응용 프로그램, 또는 VBA에서 Visual Basic에는 일반적으로 사용 되는 응용 프로그램 자동화 및 Microsoft Office 응용 프로그램 내 가장 일반적으로 다른 응용 프로그램 내부에서 매크로 대 한 고유한 기술입니다. Office의 일부분으로 VBA 함께 제공 되 고 따라서 VBA에 대 한 지원의 Office 지원 정책에 의해 제한 합니다. 그러나를 호출 하거나 Visual Basic 6.0 런타임 바이너리 및 컨트롤을 호스팅할 VBA 사용 되는 위치 하는 경우가 있습니다. 이러한 상황에서는 Visual Basic 6.0 운영 체제에서 지원 되는 런타임 파일 및 내부 지원 되는 VBA 환경을 사용 하는 경우 확장 된 파일 목록도 지원 됩니다.

VBA 내부 지원 되는 데 VB6 런타임 시나리오에는 다음과 같은 되어야 합니다.

- VB 런타임이 대 한 호스트 OS 버전은 현재 지원.
- Office VBA에 대 한 호스트 버전은 현재 지원.
- 해당 런타임 파일을 계속 지원 됩니다.

## <a name="visual-basic-script-vbscript"></a>Visual Basic 스크립트 (VBScript)

VBScript은 Visual Basic 6.0과이 지원 설명은 상관이 없습니다. 그러나 VBScript와 함께 Windows 7, Windows 8.1, Windows 10, Windows Server 2008 R2, Windows Server 2012 R2 및 Windows Server 2016 포함을 포함 하 여의 일부분으로 제공 하 고 운영 체제 지원 기간에 따라 결정 됩니다.

## <a name="third-party-components"></a>타사 구성 요소

Microsoft는 OCX/ActiveX 컨트롤과 같은 타사 구성 요소에 대 한 지원을 제공할 수 없습니다. 고객은 해당 구성 요소에 대 한 지원에 대 한 자세한 내용은 원래 컨트롤 공급 업체에 연락 하는 것이 좋습니다.

## <a name="reporting-issues-with-vb-60-applications-running-on-windows"></a>Windows에서 실행 중인 VB 6.0 응용 프로그램 문제를 보고 합니다.

나열 된 Windows 운영 체제 중 하나가 지정 된 Visual Basic 6.0을 사용 하려는 개발자는 해당 운영 체제를 설치 하 고 원래 응용 프로그램 승인 테스트를 사용 하 여 응용 프로그램 호환성 테스트를 시작 해야 합니다.

나열 된 Windows 운영 체제 중 하나에서 실행 되는 Visual Basic 6.0 응용 프로그램과 문제가 발견 하는 경우에 문제를 보고 하기 위해 일반적인 지원 채널을 수행 하십시오.

## <a name="supported-and-shipping-in-windows"></a>지원 되는 및에서 배송 창

| | | | |
|---|---|---|---|
|atl.dll|         msadcor.dll|     msorcl32.dll|   ole2.dll|
|asycfilt.dll|    msadcs.dll|      msvbvm60.dll|   ole32.dll|
|comcat.dll|      msadds.dll|      msvcirt.dll|    oleaut32.dll|
|compobj.dll|     msaddsr.dll|     msvcrt.dll|     oleaut32.dll|
|dbnmpntw.dll|    msader15.dll|    msvcrt40.dll|   oledb32.dll|
|dcomcnfg.exe|    msado15.dll|     mtxdm.dll|      oledb32r.dll|
|dllhost.exe|     msador15.dll|    mtxoci.dll|     oledlg.dll|
|ds16gt.dll|      msadrh15.dll|    odbc16gt.dll|   olepro32.dll|
|ds32gt.dll|      mscpxl32.dll|    odbc32.dll|     olethk32.dll|
|expsrv.dll|      msdadc.dll|      odbc32gt.dll|   regsvr32.exe|
|hh.exe|          msdaenum.dll|    odbcad32.exe|   rpcns4.dll|
|hhctrl.ocx|      msdaer.dll|      odbccp32.cpl|   rpcrt4.dll|
|imagehlp.dll|    msdaora.dll|     odbccp32.dll|   scrrun.dll|
|iprop.dll|       msdaosp.dll|     odbccr32.dll|   secur32.dll|
|itircl.dll|      msdaprst.dll|    odbccu32.dll|   simpdata.tlb|
|itss.dll|        msdaps.dll|      odbcint.dll|    sqloledb.dll|
|mfc40.dll|       msdasc.dll|      odbcji32.dll|   sqlsrv32.dll|
|mfc42.dll|       msdasql.dll|     odbcjt32.dll|   stdole2.tlb|
|mfc42enu.dll|    msdasqlr.dll|    odbctrac.dll|   stdole32.tlb|
|msadce.dll|      msdatsrc.tlb|    oddbse32.dll|   storage.dll|
|msadcer.dll|     msdatt.dll|      odexl32.dll|    vbajet32.dll|
|msadcf.dll|      msdfmap.dll|     odfox32.dll|    vfpodbc.dll|
|msadcfr.dll|     msdfmap.ini|     odpdx32.dll|                |
|msadco.dll|      msjtes40.dll|    odtext32.dll|               |

## <a name="supported-runtime-files-to-distribute-with-your-application"></a>응용 프로그램과 함께 배포 하려면 지원 되는 런타임 파일

| | | | |
|---|---|---|---|
|comct232.ocx |msbind.dll   |msdbrptr.dll  |msstdfmt.dll| 
|comct332.ocx |mscdrun.dll  |msflxgrd.ocx  |msstkprp.dll| 
|comctl32.ocx |mschrt20.ocx |mshflxgd.ocx  |mswcrun.dll|  
|comdlg32.ocx |mscomct2.ocx |mshtmpgr.dll  |mswinsck.ocx| 
|dbadapt.dll  |mscomctl.ocx |msinet.ocx    |picclp32.ocx| 
|dbgrid32.ocx |mscomm32.ocx |msmapi32.ocx  |richtx32.ocx| 
|dblist32.ocx |msdatgrd.ocx |msmask32.ocx  |sysinfo.ocx|  
|mci32.ocx    |msdatlst.ocx |msrdc20.ocx   |tabctl32.ocx| 
|msadodc.ocx  |msdatrep.ocx |msrdo20.dll

## <a name="unsupported-but-supported-and-compatible-updates-or-upgrades-are-available"></a>지원 되지 않는 있지만 사용할 수 있는 지원 되는 / 호환 업데이트 또는 업그레이드

| | | | |
|---|---|---|---|
|dao350.dll|   msexch35.dll| msjter35.dll| msrepl35.dll|
|mdac_typ.exe| msexcl35.dll| msjtor35.dll| mstext35.dll|
|mschart.ocx|  msjet35.dll|  msltus35.dll| msxbse35.dll|
|msdaerr.dll|  msjint35.dll| mspdox35.dll| odbctl32.dll|
|msdatl2.dll|  msjt4jlt.dll| msrd2x35.dll| oledb32x.dll|

## <a name="unsupported-runtime-files"></a>지원 되지 않는 런타임 파일

| | | | |
|---|---|---|---|
|anibtn32.ocx| spin32.ocx|   rpcltscm.dll|  rdocurs.dll|
|graph32.ocx|  gauge32.ocx|  rpcmqcl.dll|   vbar332.dll|
|keysta32.ocx| gswdll32.dll| rpcmqsvr.dll|  visdata.exe|
|autmgr32.exe| ciscnfg.exe|  rpcss.exe|     vsdbflex.srg|
|autprx32.dll| olecnv32.dll| dbmsshrn.dll|  threed32.ocx|
|racmgr32.exe| rpcltc1.dll|  dbmssocn.dll|  MSWLess.ocx|
|racreg32.dll| rpcltc5.dll|  windbver.exe|  tlbinf32.dll|
|grid32.ocx|   rpcltccm.dll| msderun.dll|   triedit.dll|
|msoutl32.ocx| rpclts5.dll|  odkob32.dll|

## <a name="localization-support-binaries"></a>지역화 지원 이진 파일

다음 이진 파일이 지역화 된 버전의 Windows 운영 체제에서 실행 되는 Visual Basic 6.0 응용 프로그램을 지원 하기 위해 필요 합니다. 지원 하지만 Windows에서 함께 제공 되지 않는. 이러한 파일은 응용 프로그램 설치 함께 출고 되어야 하는 데 필요 합니다.

### <a name="supported-runtime-files-to-distribute-with-your-application"></a>응용 프로그램과 함께 배포 하려면 지원 되는 런타임 파일

|JPN|KOR|CHT|CHS|
|---|---|---|---|
|mfc42jpn.dll|  mfc42kor.dll|  mfc42cht.dll|  mfc42chs.dll|
|scrrnjp.dll|   scrrnko.dll|   scrrncht.dll|  scrrnchs.dll|
|vb6jp.dll|     vb6ko.dll|     vb6cht.dll|    vb6chs.dll|
|cmct2jp.dll|   cmct2ko.dll|   cmct2cht.dll|  cmct2chs.dll|
|cmct3jp.dll|   cmct3ko.dll|   cmct3cht.dll|  mscc2chs.dll|
|mscc2jp.dll|   mscc2ko.dll|   mscc2cht.dll|  cmct3chs.dll|
|cmctljp.dll|   cmctlko.dll|   cmctlcht.dll|  cmctlchs.dll|
|cmdlgjp.dll|   cmdlgko.dll|   mscmccht.dll|  mscmcchs.dll|
|mscmcjp.dll|   mscmcko.dll|   cmdlgcht.dll|  cmdlgchs.dll|
|dbgrdjp.dll|   dbgrdko.dll|   dbgrdcht.dll|  dbgrdchs.dll|
|dblstjp.dll|   dblstko.dll|   dblstcht.dll|  dblstchs.dll|
|mcijp.dll|     mciko.dll|     mcicht.dll|    mcichs.dll|
|msadnjp.dll|   msadnko.dll|   msadncht.dll|  msadnchs.dll|
|adodcjp.dll|   adodcko.dll|   adodccht.dll|  adodcchs.dll|
|mschtjp.dll|   mschtko.dll|   mschtcht.dll|  mschtchs.dll|
|msch2jp.dll|   msch2ko.dll|   msch2cht.dll|  msch2chs.dll|
|mscomjp.dll|   mscomko.dll|   mscomcht.dll|  mscomchs.dll|
|datgdjp.dll|   datgdko.dll|   datgdcht.dll|  datgdchs.dll|
|datlsjp.dll|   datlsko.dll|   datlscht.dll|  datlschs.dll|
|datrpjp.dll|   datrpko.dll|   datrpcht.dll|  datrpchs.dll|
|dbrprjp.dll|   dbrprko.dll|   dbrprcht.dll|  dbrprchs.dll|
|flxgdjp.dll|   flxgdko.dll|   flxgdcht.dll|  flxgdchs.dll|
|mshfgjpn.dll|  mshfgkor.dll|  mshfgcht.dll|  mshfgchs.dll|
|htmprjp.dll|   htmprko.dll|   htmprcht.dll|  htmprchs.dll|
|inetjp.dll|    inetko.dll|    inetcht.dll|   inetchs.dll|
|msmpijp.dll|   msmpiko.dll|   msmpicht.dll|  msmpichs.dll|
|msmskjp.dll|   msmskko.dll|   msmskcht.dll|  msmskchs.dll|
|rdc20jp.dll|   rdc20ko.dll|   rdc20cht.dll|  rdc20chs.dll|
|rdo20jp.dll|   rdo20ko.dll|   rdo20cht.dll|  rdo20chs.dll|
|stdftjp.dll|   stdftko.dll|   stdftcht.dll|  stdftchs.dll|
|mswcrjp.dll|   mswcrko.dll|   mswcrcht.dll|  mswcrchs.dll|
|winskjp.dll|   winskko.dll|   winskcht.dll|  winskchs.dll|
|pcclpjp.dll|   pcclpko.dll|   pcclpcht.dll|  pcclpchs.dll|
|rchtxjp.dll|   rchtxko.dll|   rchtxcht.dll|  rchtxchs.dll|
|sysinjp.dll|   sysinko.dll|   sysincht.dll|  sysinchs.dll|
|tabctjp.dll|   tabctko.dll|   tabctcht.dll|  tabctchs.dll|

|ITA|FRA|ESP|DEU|
|---|---|---|---|
|mfc42ita.dll|  mfc42fra.dll|  mfc42esp.dll|  mfc42deu.dll|
|scrrnit.dll|   scrrnfr.dll|   scrrnes.dll|   scrrnde.dll|
|vb6it.dll|     vb6fr.dll|     vb6es.dll|     vb6de.dll|
|cmct2it.dll|   cmct2fr.dll|   cmct2es.dll|   cmct2de.dll|
|mscc2it.dll|   mscc2fr.dll|   mscc2es.dll|   mscc2de.dll|
|cmct3it.dll|   cmct3fr.dll|   cmct3es.dll|   cmct3de.dll|
|cmctlit.dll|   cmctlfr.dll|   cmctles.dll|   cmctlde.dll|
|mscmcit.dll|   mscmcfr.dll|   mscmces.dll|   mscmcde.dll|
|cmdlgit.dll|   cmdlgfr.dll|   cmdlges.dll|   cmdlgde.dll|
|dbgrdit.dll|   dbgrdfr.dll|   dbgrdes.dll|   dbgrdde.dll|
|dblstit.dll|   dblstfr.dll|   dblstes.dll|   dblstde.dll|
|mciit.dll|     mcifr.dll|     mcies.dll|     mcide.dll|
|msadnit.dll|   msadnfr.dll|   msadnes.dll|   msadnde.dll|
|adodcit.dll|   adodcfr.dll|   adodces.dll|   adodcde.dll|
|mschtit.dll|   mschtfr.dll|   mschtes.dll|   mschtde.dll|
|msch2it.dll|   msch2fr.dll|   msch2es.dll|   msch2de.dll|
|mscomit.dll|   mscomfr.dll|   mscomes.dll|   mscomde.dll|
|atgdit.dll|    datgdfr.dll|   datgdes.dll|   datgdde.dll|
|datlsit.dll|   datlsfr.dll|   datlses.dll|   datlsde.dll|
|datrpit.dll|   datrpfr.dll|   datrpes.dll|   datrpde.dll|
|dbrprit.dll|   dbrprfr.dll|   dbrpres.dll|   dbrprde.dll|
|flxgdit.dll|   flxgdfr.dll|   flxgdes.dll|   flxgdde.dll|
|mshfgit.dll|   mshfgfr.dll|   mshfges.dll|   mshfgde.dll|
|htmprit.dll|   htmprfr.dll|   htmpres.dll|   htmprde.dll|
|inetit.dll|    inetfr.dll|    inetes.dll|    inetde.dll|
|msmpiit.dll|   msmpifr.dll|   msmpies.dll|   msmpide.dll|
|msmskit.dll|   msmskfr.dll|   msmskes.dll|   msmskde.dll|
|rdc20it.dll|   rdc20fr.dll|   rdc20es.dll|   rdc20de.dll|
|rdo20it.dll|   rdo20fr.dll|   rdo20es.dll|   rdo20de.dll|
|stdftit.dll|   stdftfr.dll|   stdftes.dll|   stdftde.dll|
|mswcrit.dll|   mswcrfr.dll|   mswcres.dll|   mswcrde.dll|
|winskit.dll|   winskfr.dll|   winskes.dll|   winskde.dll|
|pcclpit.dll|   pcclpfr.dll|   pcclpes.dll|   pcclpde.dll|
|rchtxit.dll|   rchtxfr.dll|   rchtxes.dll|   rchtxde.dll|
|sysinit.dll|   sysinfr.dll|   sysines.dll|   sysinde.dll|
|tabctit.dll|   tabctfr.dll|   tabctes.dll|   tabctde.dll|

