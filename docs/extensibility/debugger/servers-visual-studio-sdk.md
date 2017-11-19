---
title: "서버 (Visual Studio SDK) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- servers, debugging
- debugging [Debugging SDK], servers
ms.assetid: 62236d64-7956-448c-9ac3-5528f3edac1d
caps.latest.revision: "17"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 496e9b361dbb7f5c3eb5cf5197a1351a1182af3e
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="servers-visual-studio-sdk"></a>서버 (Visual Studio SDK)
디버거 아키텍처를 기준으로 한 **서버**:  
  
-   포트와 포트 공급 업체의 컨테이너 이며 세션 디버그 관리자 (SDM) 포트와 포트 공급 업체와 통신 하 고 디버그 엔진을 하는 데 사용 됩니다.  
  
-   이름으로 자신을 식별 하 고 해당 포트와 포트 공급 업체를 열거할 수 있습니다.  
  
-   로 표시 됩니다는 [IDebugCoreServer2](../../extensibility/debugger/reference/idebugcoreserver2.md) 만 Visual Studio (Visual Studio 실행의 각 인스턴스에 대해 서버 인스턴스 하나)에 의해 구현 되는 인터페이스입니다.  
  
## <a name="see-also"></a>참고 항목  
 [포트](../../extensibility/debugger/ports.md)   
 [포트 공급자](../../extensibility/debugger/port-suppliers.md)   
 [디버거 개념](../../extensibility/debugger/debugger-concepts.md)   
 [IDebugCoreServer2](../../extensibility/debugger/reference/idebugcoreserver2.md)