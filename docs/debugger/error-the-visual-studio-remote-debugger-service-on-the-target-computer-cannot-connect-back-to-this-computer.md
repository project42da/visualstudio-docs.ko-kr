---
title: "오류: 대상 컴퓨터에 Visual Studio 원격 디버거 서비스가이 컴퓨터에 다시 연결할 수 없습니다 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: vs.debug.error.service_access_denied_oncallback
dev_langs:
- CSharp
- VB
- FSharp
- C++
caps.latest.revision: "12"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: f4553bceb8757b49c6d21f4bbe85e47f90e5b4dc
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="error-the-visual-studio-remote-debugger-service-on-the-target-computer-cannot-connect-back-to-this-computer"></a>오류: 대상 컴퓨터의 Visual Studio 원격 디버거 서비스가 이 컴퓨터에 다시 연결할 수 없습니다.
이 오류는 디버깅에 사용하려는 컴퓨터에 연결할 때 인증되지 않는 사용자 계정으로 Visual Studio 원격 디버거 서비스가 실행되고 있음을 의미합니다.  
  
 다음 표에는 컴퓨터에 액세스할 수 있는 계정이 나와 있습니다.  
  
|||||  
|-|-|-|-|  
||LocalSystem 계정|도메인 계정|두 컴퓨터에서 사용자 이름과 암호가 동일한 로컬 계정|  
|동일한 도메인의 두 컴퓨터|예|예|예|  
|도메인에서 양방향 트러스트가 있는 두 컴퓨터|아니요|아니요|예|  
|작업 그룹의 한 컴퓨터 또는 두 컴퓨터|아니요|아니요|예|  
|서로 다른 도메인의 컴퓨터|아니요|아니요|예|  
  
 기타  
  
-   모든 프로세스를 디버깅할 수 있으려면 Visual Studio 원격 디버거 서비스를 실행하는 데 사용되는 계정이 원격 컴퓨터의 관리자 계정이어야 합니다.  
  
-   계정 권한을 부여 받으려면 역시는 `Log on as a service` 사용 하 여 원격 컴퓨터에 대 한 권한이 **로컬 보안 정책** 관리 도구입니다.  
  
-   로컬 계정을 사용하여 컴퓨터에 액세스하는 경우 Visual Studio 원격 디버거 서비스를 로컬 계정으로 실행해야 합니다.  
  
### <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1.  원격 컴퓨터에서 Visual Studio 원격 디버거 서비스가 올바르게 설정되어 있는지 확인합니다. 자세한 내용은 참조 [원격 디버깅](../debugger/remote-debugging.md)합니다.  
  
2.  위 표에 나와 있듯이 디버거 호스트 컴퓨터에 액세스할 수 있는 계정으로 원격 디버거 서비스를 실행합니다.  
  
### <a name="to-add-log-on-as-a-service-privilege"></a>"서비스로 로그온" 권한을 추가하려면  
  
1.  에 **시작** 메뉴 선택 **제어판**합니다.  
  
2.  제어판에서 선택 **클래식 보기**필요한 경우.  
  
3.  **관리 도구**를 두 번 클릭합니다.  
  
4.  관리 도구 창에서 두 번 클릭 **로컬 보안 정책**합니다.  
  
5.  에 **로컬 보안 설정** 창 확장는 **로컬 정책** 폴더입니다.  
  
6.  클릭 **사용자 권한 할당**합니다.  
  
7.  에 **정책** 열을 두 번 클릭 **서비스로 로그온** 에서 현재 로컬 그룹 정책 할당을 볼 수는 **서비스로 로그온** 대화 상자.  
  
8.  새 사용자를 추가 하려면 클릭는 **사용자 또는 그룹 추가** 단추입니다.  
  
9. 사용자 추가 완료 했으면 클릭 **확인**합니다.  
  
### <a name="to-work-around-this-error"></a>이 오류를 해결하려면  
  
-   원격 디버깅 모니터를 서비스가 아닌 응용 프로그램으로 실행합니다.  
  
## <a name="see-also"></a>참고 항목  
 [원격 디버깅 오류 및 문제 해결](../debugger/remote-debugging-errors-and-troubleshooting.md)   
 [원격 디버깅](../debugger/remote-debugging.md)