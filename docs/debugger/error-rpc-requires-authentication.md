---
title: "오류: RPC에 인증이 필요합니다. | Microsoft Docs"
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
  - "vs.debug.error.rpc_requires_authentication"
dev_langs: 
  - "FSharp"
  - "VB"
  - "CSharp"
  - "C++"
ms.assetid: 88362b3b-8fbe-431f-96a4-80e2d822bbc7
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# 오류: RPC에 인증이 필요합니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Visual Studio 디버거에서 원격 컴퓨터에 연결할 수 없습니다.  로컬 컴퓨터에서 RPC 정책을 사용하도록 설정되어 있어 원격 디버깅을 수행할 수 없습니다.  
  
### 이 오류를 해결하려면  
  
1.  `\` *windir* `\system32\regedt32.exe`를 실행합니다.  
  
2.  `HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows NT\RPC\RestrictRemoteClients`를 찾아 삭제합니다.  
  
3.  컴퓨터를 다시 시작하여 레지스트리 변경 내용을 적용합니다.  
  
4.  문제가 지속되면 컴퓨터 구성\-\>관리 템플릿\-\>시스템\-\>원격 프로시저 호출\-\>인증되지 않은 RPC 클라이언트 제한 그룹 정책 설정에 대해 도메인 관리자에게 문의하십시오.