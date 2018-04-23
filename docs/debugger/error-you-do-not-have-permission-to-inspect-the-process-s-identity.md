---
title: '오류: 없는 프로세스를 조사할 수&#39;s identity | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: troubleshooting
dev_langs:
- CSharp
- VB
- FSharp
- C++
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0f37cf6f6a1a72435b549942fa03d821c900718a
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2018
---
# <a name="error-you-do-not-have-permission-to-inspect-the-process39s-identity"></a>오류: 없는 프로세스를 조사할 수&#39;s identity
프로세스의 ID를 검사할 수 있는 권한이 없습니다. 시스템의 구성에 문제가 있는 것 같습니다.  
  
 디버깅에 필요한 정보인 프로세스 ID를 디버거에서 검사할 수 없습니다. 이는 터미널 서비스가 해제되었기 때문일 가능성이 높습니다. 터미널 서비스는 기본적으로 사용됩니다. 이 서비스를 다시 사용하려면 다음 단계에 따릅니다.  
  
### <a name="to-enable-terminal-services"></a>터미널 서비스를 사용하려면  
  
1.  클릭 **시작** 선택한 후 **제어판**합니다.  
  
2.  제어판에서 선택 **클래식 보기로 전환**필요한 경우, 두 번 클릭 하 고 **관리 도구**합니다.  
  
3.  에 **관리 도구** 창에서 두 번 클릭 **컴퓨터 관리**합니다.  
  
4.  컴퓨터 관리 창에서 확장 된 **서비스 및 응용 프로그램** 노드.  
  
5.  아래는 **서비스 및 응용 프로그램**, 클릭 **서비스**합니다.  
  
     오른쪽 창에 서비스 목록이 표시됩니다.  
  
6.  에 **서비스** 목록에서 마우스 오른쪽 단추로 클릭 **터미널 서비스** 선택한 후 **속성**합니다.  
  
7.  에 **Terminal Services 속성** 창으로 돌아가서는 **일반** 탭 하 고 설정 **시작 유형** 를 **수동**합니다.  
  
8.  **확인**을 클릭합니다.  
  
9. 컴퓨터를 다시 시작합니다.  
  
     이렇게 해도 원격 데스크톱은 자동으로 사용되지 않습니다. 컴퓨터에서 원격 데스크톱을 사용하려면 다음 절차를 추가로 수행합니다.  
  
### <a name="to-enable-remote-desktop"></a>원격 데스크톱을 사용하려면  
  
1.  클릭 **시작** 마우스 오른쪽 단추로 클릭 한 다음 **내 컴퓨터**합니다.  
  
2.  **속성**을 선택합니다.  
  
     **시스템 속성** 창이 표시 됩니다.  
  
3.  클릭 **원격**합니다.  
  
4.  아래 **원격 데스크톱**선택, **사용자가이 컴퓨터에 원격으로 연결할 수 있도록**합니다.  
  
5.  **확인**을 클릭합니다.  
  
## <a name="see-also"></a>참고 항목  
 [원격 디버깅 오류 및 문제 해결](../debugger/remote-debugging-errors-and-troubleshooting.md)