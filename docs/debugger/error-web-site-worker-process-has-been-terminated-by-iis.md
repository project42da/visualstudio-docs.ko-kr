---
title: "오류: 웹 사이트 작업자 프로세스에 의해 종료 되었습니다 IIS | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: vs.debug.error.web_server_process_terminated
dev_langs:
- CSharp
- VB
- FSharp
- C++
caps.latest.revision: "20"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: fb7a0220cf6650aeeb12ec6549d112a39918de3f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="error-web-site-worker-process-has-been-terminated-by-iis"></a>오류: IIS에서 웹 사이트 작업자 프로세스를 종료했습니다.
디버거가 웹 사이트에서 코드 실행을 중지했습니다. 이로 인해 IIS(인터넷 정보 서비스)에서는 작업자 프로세스가 응답을 중지한 것으로 가정하여 작업자 프로세스를 종료했습니다.  
  
 디버깅을 계속하려면 작업자 프로세스를 계속하도록 IIS를 구성해야 합니다. 이 오류 메시지는 IIS 7 이전 버전의 IIS에서는 표시되지 않습니다.  
  
### <a name="to-configure-iis-7-to-allow-the-worker-process-to-continue"></a>작업자 프로세스를 계속하도록 IIS 7을 구성하려면  
  
1.  열기는 **관리 도구** 창.  
  
    1.  클릭 **시작**를 선택한 후 **제어판**합니다.  
  
    2.  **제어판**, 선택 **클래식 보기로 전환**필요한 경우, 두 번 클릭 하 고 **관리 도구**합니다.  
  
2.  에 **관리 도구** 창에서 두 번 클릭 **인터넷 정보 서비스 (IIS) 관리자**합니다.  
  
     IIS 관리자가 열립니다.  
  
3.  에 **연결** 창에서 확장 하 고는 \<컴퓨터 이름 > 필요한 경우 노드.  
  
4.  아래는 \<컴퓨터 이름 > 노드를 클릭 하 여 **응용 프로그램 풀**합니다.  
  
5.  에 **응용 프로그램 풀** 목록에서 응용 프로그램을 실행 하는 풀의 이름을 마우스 오른쪽 단추로 클릭 하 고 클릭 **고급 설정**합니다.  
  
6.  에 **고급 설정** 대화 상자를 찾습니다는 **프로세스 모델** 섹션을 선택한 다음 작업 중 하나를 수행 합니다.  
  
    -   설정 **Ping 사용** 를 **False**합니다.  
  
    -   설정 **Ping 최대 응답 시간** 90 초 보다 큰 값으로.  
  
     설정 **Ping 사용** 를 **False** 작업자 프로세스가 계속 실행 되 고 디버깅된 된 프로세스를 중지할 때까지 작업자 프로세스가 활성 상태로 유지 하는지 여부를 확인 하거나 IIS를 중지 합니다. 설정 **Ping 최대 응답 시간** 큰 값으로 IIS 작업자 프로세스 모니터링을 계속 허용 합니다.  
  
7.  클릭 **확인** 를 닫으려면는 **고급 설정** 대화 상자.  
  
8.  IIS 관리자를 닫습니다 및 **관리 도구** 창.  
  
## <a name="see-also"></a>참고 항목  
 [원격 디버깅 오류 및 문제 해결](../debugger/remote-debugging-errors-and-troubleshooting.md)