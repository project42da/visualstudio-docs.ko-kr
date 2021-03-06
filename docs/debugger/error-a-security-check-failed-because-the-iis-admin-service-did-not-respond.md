---
title: '오류: IIS Admin Service가 응답 하지 않아서 보안 검사에 실패 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: troubleshooting
f1_keywords:
- vs.debug.error.iis_not_responding
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
ms.openlocfilehash: a3b0b3412c450976cb15211813de32ab6e78eaa9
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2018
---
# <a name="error-a-security-check-failed-because-the-iis-admin-service-did-not-respond"></a>오류: IIS 관리자 서비스에서 응답이 없기 때문에 보안 검사에 실패했습니다.
이 오류는 IIS 관리자 서비스에서 응답하지 않을 때 발생합니다. 일반적으로 이는 설치한 IIS에 문제가 있음을 나타냅니다. 먼저, 서비스를 사용 하 여 실행 중인지를 확인는 **서비스** 에서 도구 **관리 도구**합니다.  
  
### <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   IIS를 사용 하 여 다시 설치는 **프로그램 추가 / 제거** 제어판 합니다.  
  
-   -또는-  
  
-   제어판의 프로그램 추가/제거를 사용하여 컴퓨터에서 IIS를 제거합니다. IIS를 제거했는데도 문제가 해결되지 않으면 레지스트리에서 다음 키가 더 이상 표시되지 않는지 확인합니다.  
  
    ```  
    HKEY_CLASSES_ROOT\CLSID\{A9E69610-B80D-11D0-B9B9-00A0C922E750}  
    ```  
  
     -또는-  
  
-   제어판의 관리 도구를 사용하여 IIS 관리자 서비스를 사용하지 않도록 설정합니다. 이렇게 하면 사용자의 컴퓨터에서 IIS를 사용할 수 없습니다.  
  
     이 세 단계 중 하나를 수행한 후에 컴퓨터를 다시 시작합니다.  
  
     자세한 내용은 IIS 설명서를 참조하십시오.  
  
## <a name="see-also"></a>참고 항목  
 [웹 응용 프로그램 디버그: 오류 및 문제 해결](../debugger/debugging-web-applications-errors-and-troubleshooting.md)