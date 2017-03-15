---
title: "디버거 외부에서 프로그램을 실행하는 경우 액세스 위반을 어떻게 디버깅할 수 있습니까? | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.debug.access"
dev_langs: 
  - "FSharp"
  - "VB"
  - "CSharp"
  - "C++"
  - "C++"
helpviewer_keywords: 
  - "액세스 위반 디버깅"
  - "디버깅[Visual Studio], 액세스 위반"
ms.assetid: 780a298a-132e-4245-8370-8c82ca27c6c1
caps.latest.revision: 19
caps.handback.revision: 19
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# 디버거 외부에서 프로그램을 실행하는 경우 액세스 위반을 어떻게 디버깅할 수 있습니까?
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

## 문제 설명  
 프로그램이 Visual Studio 환경에서 올바르게 실행됩니다. 그러나 Windows 운영 체제에서 독립 실행형으로 실행하면 액세스 위반이 발생합니다.  이 문제를 어떻게 디버깅할 수 있습니까?  
  
## 해결책  
 [Just\-in\-time debugging](../debugger/just-in-time-debugging-in-visual-studio.md) 옵션을 설정한 다음 액세스 위반이 발생할 때까지 프로그램을 독립 실행형으로 실행합니다.  그런 다음 **액세스 위반** 대화 상자에서 **취소**를 클릭하여 디버거를 시작할 수 있습니다.  
  
 또는 기술 자료 문서 Q133174 "How to Locate Where a General Protection \(GP\) Fault Occurs."를 참조하십시오. 기술 자료 문서는 MSDN 라이브러리 CD 또는 [http:\/\/support.microsoft.com\/](http://support.microsoft.com/)에서 찾아 볼 수 있습니다.  
  
## 참고 항목  
 [네이티브 코드 디버깅 FAQ](../debugger/debugging-native-code-faqs.md)   
 [네이티브 코드 디버깅](../debugger/debugging-native-code.md)