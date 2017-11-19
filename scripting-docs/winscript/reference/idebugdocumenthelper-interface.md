---
title: "IDebugDocumentHelper 인터페이스 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords: IDebugDocumentHelper interface
ms.assetid: b652a31e-b87b-45f1-b586-94f2b6e822db
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: baadcc1e2dba0b07e132298167b9b711e40cd912
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="idebugdocumenthelper-interface"></a>IDebugDocumentHelper 인터페이스
같은 스마트 호스트 하는 데 필요한 여러 인터페이스에 대 한 구현을 제공는 `IDebugDocument`, `IDebugDocumentContext`, `IDebugDocumentProvider`, `IDebugDocumentText`, 및 `IDebugDocumentTextEvents` 인터페이스입니다.  
  
 상속 된 메서드 외에도 `IUnknown`, `IDebugDocumentHelper` 인터페이스는 다음 메서드를 노출 합니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[IDebugDocumentHelper::Init](../../winscript/reference/idebugdocumenthelper-init.md)|이름과 초기 특성으로 디버그 문서 도우미를 초기화합니다.|  
|[IDebugDocumentHelper::Attach](../../winscript/reference/idebugdocumenthelper-attach.md)|이 문서는 문서 트리에서 추가합니다.|  
|[IDebugDocumentHelper::Detach](../../winscript/reference/idebugdocumenthelper-detach.md)|이 문서는 문서 트리에서 제거합니다.|  
|[IDebugDocumentHelper::AddUnicodeText](../../winscript/reference/idebugdocumenthelper-addunicodetext.md)|종료 유니코드 문자열을 추가이 문서의.|  
|[IDebugDocumentHelper::AddDBCSText](../../winscript/reference/idebugdocumenthelper-adddbcstext.md)|종료 하려면 DBCS 문자열 추가 합니다.이 문서의.|  
|[IDebugDocumentHelper::SetDebugDocumentHost](../../winscript/reference/idebugdocumenthelper-setdebugdocumenthost.md)|설정 된 `IDebugDocumentHost` 이 문서에 대 한 합니다.|  
|[IDebugDocumentHelper::AddDeferredText](../../winscript/reference/idebugdocumenthelper-adddeferredtext.md)|지정된 된 텍스트를 사용할 수 있지만 문자를 제공 하지 않으며 도우미를에 알립니다.|  
|[IDebugDocumentHelper::DefineScriptBlock](../../winscript/reference/idebugdocumenthelper-definescriptblock.md)|특정 문자 범위는 특정된 스크립트 엔진에서 처리 하는 스크립트 블록에서 도우미를 나타냅니다.|  
|[IDebugDocumentHelper::SetDefaultTextAttr](../../winscript/reference/idebugdocumenthelper-setdefaulttextattr.md)|스크립트 블록에 있지 않은 텍스트에 사용할 기본 특성을 설정 합니다.|  
|[IDebugDocumentHelper::SetTextAttributes](../../winscript/reference/idebugdocumenthelper-settextattributes.md)|텍스트 범위에 특성을 설정합니다.|  
|[IDebugDocumentHelper::SetLongName](../../winscript/reference/idebugdocumenthelper-setlongname.md)|문서에 대 한 긴 이름을 설정합니다.|  
|[IDebugDocumentHelper::SetShortName](../../winscript/reference/idebugdocumenthelper-setshortname.md)|문서에 대 한 약식 이름을 설정합니다.|  
|[IDebugDocumentHelper::SetDocumentAttr](../../winscript/reference/idebugdocumenthelper-setdocumentattr.md)|이 문서에 대 한 특성을 설정합니다.|  
|[IDebugDocumentHelper::GetDebugApplicationNode](../../winscript/reference/idebugdocumenthelper-getdebugapplicationnode.md)|이 문서에 해당 디버그 응용 프로그램 노드를 반환 합니다.|  
|[IDebugDocumentHelper::GetScriptBlockInfo](../../winscript/reference/idebugdocumenthelper-getscriptblockinfo.md)|문자 및 스크립트 엔진에 해당 하는 스크립트 블록의 범위를 검색 합니다.|  
|[IDebugDocumentHelper::CreateDebugDocumentContext](../../winscript/reference/idebugdocumenthelper-createdebugdocumentcontext.md)|새 디버그 문서 컨텍스트를 만듭니다.|  
|[IDebugDocumentHelper::BringDocumentToTop](../../winscript/reference/idebugdocumenthelper-bringdocumenttotop.md)|이 문서 디버거에서 상위 사용자 인터페이스입니다.|  
|[IDebugDocumentHelper::BringDocumentContextToTop](../../winscript/reference/idebugdocumenthelper-bringdocumentcontexttotop.md)|디버거 사용자 인터페이스에서 위쪽을이 설명서의 컨텍스트를 제공합니다.|