---
title: "IApplicationDebuggerUI 인터페이스 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- IApplicationDebuggerUI interface
ms.assetid: b8828817-ca24-4012-802c-7dcaeea65dc8
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: dbaa04f6790ffc4d80447a6745ca82cc8dba6802
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iapplicationdebuggerui-interface"></a>IApplicationDebuggerUI 인터페이스
디버거 통합된 개발 환경 (IDE)에서 구현 된 (외에 `IApplicationDebugger`) 디버거 사용자 인터페이스 (UI)를 보다 상세하게 외부 구성 요소를 제공 합니다.  
  
 상속 된 메서드 외에도 `IUnknown`, `IApplicationDebuggerUI` 인터페이스는 다음 메서드를 노출 합니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[IApplicationDebuggerUI::BringDocumentToTop](../../winscript/reference/iapplicationdebuggerui-bringdocumenttotop.md)|디버거에서 위쪽으로 지정 된 디버그 문서를 포함 하 여 창 사용자 인터페이스를 제공 합니다.|  
|[IApplicationDebuggerUI::BringDocumentContextToTop](../../winscript/reference/iapplicationdebuggerui-bringdocumentcontexttotop.md)|디버거 사용자 인터페이스에서 위쪽으로 지정한 문서 컨텍스트를 포함 하는 창을 시작 하 고 컨텍스트에 창을 스크롤합니다.|