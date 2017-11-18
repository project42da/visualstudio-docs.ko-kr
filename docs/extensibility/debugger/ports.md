---
title: "포트 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ports
- debugging [Debugging SDK], ports
ms.assetid: 1d7f3aa7-7eff-4cab-bc53-0a566b1a9363
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 926f5e9a80a91da57d843c11175865f78775e38c
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="ports"></a>포트
디버거 아키텍처를 기준으로 한 **포트**:  
  
-   일련의 프로세스에 대 한 컨테이너는 서버에서 실행 됩니다. 예를 들어 포트 직렬 케이블을 통해 Windows CE 기반 장치에 또는 DCOM이 아닌 네트워크로 연결 된 컴퓨터에 대 한 연결을 나타낼 수 있습니다. 로컬 포트 라는 하나의 특별 한 포트에는 로컬 컴퓨터에서 실행 중인 모든 프로세스가 포함 되어 있습니다.  
  
-   이름이 나 식별자 자신을 식별할 수 있습니다.  
  
-   수 포트에서 실행 중인 모든 프로세스를 열거 하 고 실행 되 고 이러한 프로세스를 종료 합니다.  
  
-   로 표시 됩니다는 [IDebugPort2](../../extensibility/debugger/reference/idebugport2.md) 전달 하 여 생성 된 인터페이스는 [IDebugPortRequest2](../../extensibility/debugger/reference/idebugportrequest2.md) 인수를 [포트 추가](../../extensibility/debugger/reference/idebugportsupplier2-addport.md)합니다.  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]모든 Windows 기반 프로세스, 네이티브 및 관리를 처리 하는 기본 포트를 제공 합니다. 사용자 지정 포트를 Windows 기반이 아닌 외부 장치 연결에 대 한 구현 되어야 합니다. 이러한 사용자 지정 포트를 제공 하려면 사용자 지정 포트 공급자도 구현 해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [서버](../../extensibility/debugger/servers-visual-studio-sdk.md)   
 [프로세스](../../extensibility/debugger/processes.md)   
 [디버거 개념](../../extensibility/debugger/debugger-concepts.md)   
 [IDebugPort2](../../extensibility/debugger/reference/idebugport2.md)   
 [IDebugPortRequest2](../../extensibility/debugger/reference/idebugportrequest2.md)   
 [포트 추가](../../extensibility/debugger/reference/idebugportsupplier2-addport.md)