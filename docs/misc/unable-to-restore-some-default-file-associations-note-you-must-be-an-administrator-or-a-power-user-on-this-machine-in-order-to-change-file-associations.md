---
title: "일부 기본 파일 연결을 복원할 수 없습니다. 참고: 파일 연결을 변경하려면 이 컴퓨터에서 관리자나 고급 사용자여야 합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VS.Message.0x00006A85"
  - "VS_E_RESTOREFILEASSOCS"
ms.assetid: 449c5608-83e3-4ddd-91f1-1061916995b3
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# 일부 기본 파일 연결을 복원할 수 없습니다. 참고: 파일 연결을 변경하려면 이 컴퓨터에서 관리자나 고급 사용자여야 합니다.
이 오류는 devenv 명령줄 스위치 \/AssociateFiles를 사용했지만 현재 사용자 권한으로는 레지스트리의 HKEY\_CLASSES\_ROOT 섹션에 액세스할 수 없는 경우에 발생합니다.[!INCLUDE[wiprlhext](../debugger/includes/wiprlhext_md.md)]에서 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]를 실행하는 경우 \/AssociateFiles\(devenv.exe\) 스위치를 사용하려면 devenv를 관리자로 실행해야 합니다.  
  
### 이 오류를 해결하려면  
  
-   관리 자격 증명으로 변경하고 다시 시도하세요.  
  
## 참고 항목  
 [User Rights and Visual Studio](http://msdn.microsoft.com/ko-kr/d5c55084-1e7b-4b61-b478-137db01c0fc0)   
 [Devenv 명령줄 스위치](../ide/reference/devenv-command-line-switches.md)