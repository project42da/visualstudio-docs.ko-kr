---
title: "공급자 포트 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- port suppliers
- debugging [Debugging SDK], port suppliers
ms.assetid: a8f3db96-1a13-4e93-9ef6-0861880369e0
caps.latest.revision: "15"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 0cab184b0ecf4c4971b116cc9dfde26d8f80b45f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="port-suppliers"></a>포트 공급자
디버거 아키텍처를 기준으로 한 **포트 공급자**:  
  
-   서버를 포함 하 고 해당 서버에 요청에서 포트를 제공 합니다.  
  
-   추가 하 고 포함 하는 서버에서 포트를 제거할 수 있습니다.  
  
-   서버에 제공 되는 모든 포트를 열거할 수 있습니다.  
  
-   로 표시 됩니다는 [IDebugPortSupplier2](../../extensibility/debugger/reference/idebugportsupplier2.md) 레지스트리를 통해 Visual Studio와 함께 등록 되는 인터페이스입니다. 이 인터페이스를 호출 하 여 얻을 수 있습니다 [GetPortSupplier](../../extensibility/debugger/reference/idebugcoreserver2-getportsupplier.md)합니다.  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]기본 포트 공급 업체와 기본 포트를 제공합니다. 사용자 지정 포트를 구현 하는 경우 이러한 사용자 지정 포트를 제공 하도록 구현 해야 하는 사용자 지정 포트 공급자도 필요 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [서버](../../extensibility/debugger/servers-visual-studio-sdk.md)   
 [포트](../../extensibility/debugger/ports.md)   
 [디버거 개념](../../extensibility/debugger/debugger-concepts.md)   
 [IDebugPortSupplier2](../../extensibility/debugger/reference/idebugportsupplier2.md)   
 [GetPortSupplier](../../extensibility/debugger/reference/idebugcoreserver2-getportsupplier.md)