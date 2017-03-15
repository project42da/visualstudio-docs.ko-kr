---
title: "경고: 스크립트 디버깅 사용 안 함 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.debug.scriptdisabled"
dev_langs: 
  - "FSharp"
  - "VB"
  - "CSharp"
  - "C++"
ms.assetid: 323d2b1d-52a4-42f7-b4ad-96b4b0c23b8d
caps.latest.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 7
---
# 경고: 스크립트 디버깅 사용 안 함
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Internet Explorer에서는 현재 스크립트 디버깅을 사용하지 않습니다.  
  
 이 경고는 Internet Explorer에서 스크립트 디버깅을 사용할 수 없는 상태에서 스크립트를 디버깅할 때 발생합니다.  보안상의 이유로 Internet Explorer에서는 스크립트 디버깅을 기본적으로 사용하지 않습니다.  
  
### Internet Explorer에서 스크립트 디버깅을 사용하려면  
  
1.  Internet Explorer의 **도구** 메뉴에서 **인터넷 옵션**을 선택합니다.  
  
2.  **인터넷 옵션** 대화 상자에서 **고급** 탭을 클릭합니다.  
  
3.  **고급** 탭의 **설정** 상자에서 **탐색** 범주를 찾습니다.  
  
4.  **스크립트 디버깅 사용 안 함\(Internet Explorer\)**의 선택을 취소합니다.  
  
5.  **확인**을 클릭합니다.  
  
6.  Internet Explorer를 종료하고 다시 시작합니다.  
  
     그러면 새 설정이 적용됩니다.  
  
## 참고 항목  
 [방법: 스크립트에 연결](../debugger/how-to-attach-to-script.md)