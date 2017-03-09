---
title: "이 작업을 수행하려면 추가 권한이 필요합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.UACDialog"
ms.assetid: a03d3509-5e6e-411a-9aec-0766d7ee3a0e
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# 이 작업을 수행하려면 추가 권한이 필요합니다.
작업을 완료할 수 있는 권한이 계정에는 사용자가 Visual Studio 명령을 호출 하는 경우이 오류가 표시 됩니다.  
  
 일부 Visual Studio 명령은 명령이 모든 필요한 파일 및 레지스트리 키를 읽거나 쓰려고 사용할 수 있도록 충분 한 사용자 액세스 권한이 있는 계정으로 실행 되어야 합니다.  이러한 권한을 얻으려면 종료 하 고으로 관리자와 같은 액세스 권한이 높은 계정으로 Visual Studio 다시 합니다.  
  
 Visual Studio 실행 하는 경우 사용 권한에 대 한 자세한 내용은 [사용자 권한](../ide/user-permissions-and-visual-studio.md).  
  
### 이 오류를 해결하려면  
  
1.  대화 상자에서 **다른 계정을 사용하여 다시 시작**을 클릭합니다.  
  
     이 현재 로드 된 솔루션을 저장할 것인지 묻는 메시지가 및 다음 Visual Studio 닫고 다른 계정으로 전환 하 라는 메시지가 다시 시작 합니다.  
  
2.  로그인 대화 상자에서 Administrator와 같이 이전 계정보다 더 높은 권한이 있는 계정으로 로그인합니다.  
  
     Visual Studio 시작할 때 마지막 솔루션 및 명령줄 다시 로드 합니다.  
  
> [!NOTE]
>  더 높은 권한을 가진 계정 사용 하 여 로깅 Visual Studio 명령 작동 하는지 반드시 보증 하지 않습니다.  관리자 계정을 사용 하는 경우에 일부 명령을 성공적으로 실행할 수 있습니다.