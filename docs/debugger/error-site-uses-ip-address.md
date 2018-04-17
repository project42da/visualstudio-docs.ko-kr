---
title: '오류: 사이트 사용 하 여 IP 주소 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: reference
f1_keywords:
- vs.debug.error.webdbg_siteusesipaddress
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugger, Web application errors
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1c97d9eb715711b3315c97a95503489b87f323f0
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="error-site-uses-ip-address"></a>오류: 사이트에서 IP 주소를 사용합니다.
이 오류는 디버거에서 IP 주소를 사용하는 웹 응용 프로그램에 자동으로 연결하려고 할 때 발생합니다. 변경 하는 경우이 발생 **웹 사이트 확인** 를 **특정 IP 주소를 사용 하 여** IIS에서 합니다.  
  
 자동 연결이 제대로 동작하기 위해서는 컴퓨터 이름뿐 아니라 특정 IP 주소도 함께 사용하여 프로젝트를 만들어야 합니다. 그렇지 않으면 디버거에서 컴퓨터 이름을 localhost로 변경하므로 DEBUG 동사를 IIS로 보낼 수 없게 됩니다.  
  
### <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1.  연결 대신 사용 하 여 수동 연결 (디버그 메뉴에서 선택 **프로세스에 연결**).  
  
     또는  
  
2.  변경 된 **IIS 웹 사이트 확인** 설정 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [웹 응용 프로그램 디버그: 오류 및 문제 해결](../debugger/debugging-web-applications-errors-and-troubleshooting.md)