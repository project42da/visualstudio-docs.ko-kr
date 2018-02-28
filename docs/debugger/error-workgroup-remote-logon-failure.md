---
title: "오류: 작업 그룹 원격 로그온 실패 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vs.debug.error.workgroup_remote_logon_failure
dev_langs:
- CSharp
- VB
- FSharp
- JScript
- C++
helpviewer_keywords:
- logon failure, remote debugging
- remote debugging, logon failure
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 38ec2de37279e1f383751c9652aeeac74473c50f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="error-workgroup-remote-logon-failure"></a>오류: 작업 그룹 원격 로그온 실패
이 오류의 의미는 다음과 같습니다.  
  
 로그온 실패: 사용자 이름을 알 수 없거나 암호가 잘못되었습니다.  
  
 **원인**  
  
 이 오류는 작업 그룹의 컴퓨터에서 디버깅하는 경우 원격 컴퓨터에 연결할 때 발생할 수 있습니다. 이 오류가 발생하는 원인은 다음과 같습니다.  
  
-   원격 컴퓨터에 이름과 암호가 일치하는 계정이 없습니다.  
  
-   기본적으로 인해이 오류가 발생할 수 있습니다는 Visual Studio 컴퓨터와 원격 컴퓨터 둘 다 작업 그룹에 있는 경우 **로컬 보안 정책** 원격 컴퓨터에서 설정 합니다. 에 대 한 기본 설정은 **로컬 보안 정책** 설정은 **게스트 전용-로컬 사용자를 게스트로 인증**합니다. 이 설치 프로그램을 디버깅 하려면 원격 컴퓨터의 설정을 변경 해야 **일반-로컬 사용자를 그대로 인증**합니다.  
  
> [!NOTE]
>  다음 작업을 수행하려면 관리자 권한이 있어야 합니다.  
  
### <a name="to-open-the-local-security-policy-window"></a>로컬 보안 정책 창을 열려면  
  
1.  시작 된 **secpol.msc** Microsoft Management Console 스냅인입니다. Windows 검색, Windows 실행 상자 또는 명령 프롬프트에 secpol.msc를 입력합니다.  
  
### <a name="to-add-user-rights-assignments"></a>사용자 권한 할당을 추가하려면  
  
1.  열기는 **로컬 보안 정책** 창.  
  
2.  확장 된 **로컬 정책** 폴더입니다.  
  
3.  클릭 **사용자 권한 할당**합니다.  
  
4.  에 **정책** 열을 두 번 클릭 **프로그램 디버그** 현재 로컬 그룹 정책 할당을 볼 수는 **로컬 보안 정책 설정** 대화 상자.  
  
     ![로컬 보안 정책 사용자 권한](../debugger/media/dbg_err_localsecuritypolicy_userrightsdebugprograms.png "DBG_ERR_LocalSecurityPolicy_UserRightsDebugPrograms")  
  
5.  새 사용자를 추가 하려면 클릭는 **사용자 또는 그룹 추가** 단추입니다.  
  
### <a name="to-change-the-sharing-and-security-model"></a>공유 및 보안 모델을 변경하려면  
  
1.  열기는 **로컬 보안 정책** 창.  
  
2.  확장 된 **로컬 정책** 폴더입니다.  
  
3.  클릭 **보안 옵션**합니다.  
  
4.  에 **정책** 열을 두 번 클릭 **네트워크 액세스: 로컬 계정에 대 한 공유 및 보안 모델**합니다.  
  
5.  에 **네트워크 액세스: 로컬 계정에 대 한 공유 및 보안 모델** 대화 상자에서 값을 변경 **일반-로컬 사용자를 그대로 인증** 클릭는 **적용**단추입니다.  
  
     ![로컬 보안 정책 보안 옵션](../debugger/media/dbg_err_localsecuritypolicy_securityoptions_networkaccess.png "DBG_ERR_LocalSecurityPolicy_SecurityOptions_NetworkAccess")  
  
## <a name="see-also"></a>참고 항목  
 [원격 디버깅 오류 및 문제 해결](../debugger/remote-debugging-errors-and-troubleshooting.md)   
 [원격 디버깅](../debugger/remote-debugging.md)