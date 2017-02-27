---
title: "오류: IIS 관리자 서비스에서 응답이 없기 때문에 보안 검사에 실패했습니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.debug.error.iis_not_responding"
dev_langs: 
  - "FSharp"
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "디버거, 웹 응용 프로그램 오류"
ms.assetid: 6060e94e-71dc-49f2-bb59-2584216eadbf
caps.latest.revision: 10
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 10
---
# 오류: IIS 관리자 서비스에서 응답이 없기 때문에 보안 검사에 실패했습니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이 오류는 IIS 관리자 서비스에서 응답하지 않을 때 발생합니다.  일반적으로 이는 설치한 IIS에 문제가 있음을 나타냅니다.  먼저 **관리 도구**에서 **서비스** 도구를 사용하여 서비스가 실행 중인지 확인하십시오.  
  
### 이 오류를 해결하려면  
  
-   제어판의 **프로그램 추가\/제거**를 사용하여 IIS를 다시 설치합니다.  
  
-   또는  
  
-   제어판의 프로그램 추가\/제거를 사용하여 컴퓨터에서 IIS를 제거합니다.  IIS를 제거했는데도 문제가 해결되지 않으면 레지스트리에서 다음 키가 더 이상 표시되지 않는지 확인합니다.  
  
    ```  
    HKEY_CLASSES_ROOT\CLSID\{A9E69610-B80D-11D0-B9B9-00A0C922E750}  
    ```  
  
     또는  
  
-   제어판의 관리 도구를 사용하여 IIS 관리자 서비스를 사용하지 않도록 설정합니다.  이렇게 하면 사용자의 컴퓨터에서 IIS를 사용할 수 없습니다.  
  
     이 세 단계 중 하나를 수행한 후에 컴퓨터를 다시 시작합니다.  
  
     자세한 내용은 IIS 설명서를 참조하십시오.  
  
## 참고 항목  
 [웹 응용 프로그램 디버깅: 오류 및 문제 해결](../debugger/debugging-web-applications-errors-and-troubleshooting.md)