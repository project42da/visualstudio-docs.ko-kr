---
title: 원격 디버거 다운로드
description: 원격 디버거에 대 한 다운로드 링크
services: ''
author: mikejo5000
ms.service: ''
ms.topic: include
ms.date: 05/23/2018
ms.author: mikejo
ms.custom: include file
ms.openlocfilehash: 358dc0b457381bb56532e6cae1156aac9ea2dba2
ms.sourcegitcommit: d1824ab926ebbc4a8057163e0edeaf35cec57433
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/24/2018
---
1.  장치 또는 서버 디버깅 하려는 컴퓨터 (을 하지 않고 Visual Studio를 실행 하는 컴퓨터)에서 올바른 버전을의 원격 도구를 가져옵니다.

    |버전|링크|노트|
    |-|-|-|
    |Visual Studio 2017 (최신 버전)|[원격 도구](https://www.visualstudio.com/downloads/?q=remote+tools#remote-tools-for-visual-studio-2017)|항상 장치 운영 체제 (x86 또는 x64)를 일치 하는 버전을 다운로드 합니다. Windows Server에서 참조 [파일 다운로드를 차단 해제](../../debugger/remote-debugging.md#unblock_msvsmon) 에 대 한 도움말을 원격 도구를 다운로드 합니다.|
    |Visual Studio 2017 (구)|[원격 도구](https://my.visualstudio.com/Downloads?q=remote%20tools%20visual%20studio%202017)|Visual Studio 2017의 이전 릴리스에 대 한 원격 도구가 My.VisualStudio.com에서 제공 됩니다. 메시지가 표시 되 면 조인 무료 Visual Studio Dev Essentials 그룹 또는 Visual Studio 구독을 사용 하 여 로그인 id입니다. Windows Server에서 참조 [파일 다운로드를 차단 해제](../../debugger/remote-debugging.md#unblock_msvsmon) 에 대 한 도움말을 원격 도구를 다운로드 합니다.|
    |Visual Studio 2015 (구)|[원격 도구](https://my.visualstudio.com/Downloads?q=remote%20tools%20visual%20studio%202015)|메시지가 표시 되 면 조인 무료 Visual Studio Dev Essentials 그룹 또는 Visual Studio 구독을 사용 하 여 로그인 id입니다. Windows Server에서 참조 [파일 다운로드를 차단 해제](../../debugger/remote-debugging.md#unblock_msvsmon) 에 대 한 도움말을 원격 도구를 다운로드 합니다.|
    |Visual Studio 2013|[원격 도구](https://msdn.microsoft.com/library/bt727f1t(v=vs.120).aspx#BKMK_Installing_the_Remote_Tools)|Visual Studio 2013 설명서에서 페이지를 다운로드 합니다.|
    |Visual Studio 2012|[원격 도구](https://msdn.microsoft.com/library/bt727f1t(v=vs.110).aspx#BKMK_Installing_the_Remote_Tools)|Visual Studio 2012 설명서에서 페이지를 다운로드 합니다.|
  
2.  다운로드 페이지에서 운영 체제 (x 86, x64 또는 ARM)와 일치 하는 버전의 도구를 선택 하 고 원격 도구를 다운로드 합니다.
  
    > [!IMPORTANT]
    >  Visual Studio 버전에 일치 하는 가장 최신 버전의 원격 도구를 설치 하는 것이 좋습니다. 버전이 일치 하지 않는 권장 되지 않습니다. 또한 설치 하려는 운영 체제와 동일한 아키텍처가 있는 원격 도구를 설치 해야 합니다. 즉, 64 비트 운영 체제를 실행 하는 원격 컴퓨터에서 32 비트 응용 프로그램을 디버깅 하려면 원격 컴퓨터에서 64 비트 버전의 원격 도구를 설치 해야 합니다. 
    >   
    >  화면 3 x64 ARM에서 전환 아키텍처. ARM 버전의 원격 도구에 대 한 Visual Studio 2017 ´ ù. Visual Studio 2015에 대 한 Visual Studio 2015 RTW 다운로드에 ARM 버전을 찾습니다.
  
3.  실행 파일을 다운로드 했으면 다음 섹션으로 이동 하 고 설치 지침을 따릅니다.

원격 컴퓨터에 원격 디버거 (msvsmon.exe)를 복사 하 고 실행 하려고 하는 경우 주의 해야 하는 **원격 디버거 구성 마법사** (**rdbgwiz.exe**) 다운로드 하는 경우에 설치 되는 도구입니다. 특히 원격 디버거가 서비스로 실행 되도록 하는 경우 나중에 구성에 대 한 마법사를 사용 해야 합니다. 자세한 내용은 참조 [구성 (선택 사항) 원격 디버거를 서비스로](../../debugger/remote-debugging.md#bkmk_configureService)합니다.
