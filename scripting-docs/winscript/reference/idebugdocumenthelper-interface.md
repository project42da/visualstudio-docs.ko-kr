---
title: "IDebugDocumentHelper 인터페이스 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
helpviewer_keywords: 
  - "IDebugDocumentHelper 인터페이스"
ms.assetid: b652a31e-b87b-45f1-b586-94f2b6e822db
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugDocumentHelper 인터페이스
스마트 호스트에 필요한 많은 인터페이스에 대 한 구현을 제공 된 `IDebugDocument`, `IDebugDocumentContext`, `IDebugDocumentProvider`, `IDebugDocumentText`, 및 `IDebugDocumentTextEvents` 인터페이스.  
  
 `IUnknown`에서 상속되는 메서드 외에 `IDebugDocumentHelper` 인터페이스는 다음 메서드를 노출합니다.  
  
## Vtable 순서의 메서드  
  
|메서드|설명|  
|---------|--------|  
|[IDebugDocumentHelper::Init](../../winscript/reference/idebugdocumenthelper-init.md)|디버그 문서 도우미 이름과 초기 특성을 초기화합니다.|  
|[IDebugDocumentHelper::Attach](../../winscript/reference/idebugdocumenthelper-attach.md)|이 문서는 문서 트리에 추가합니다.|  
|[IDebugDocumentHelper::Detach](../../winscript/reference/idebugdocumenthelper-detach.md)|이 문서는 문서 트리에서 제거 됩니다.|  
|[IDebugDocumentHelper::AddUnicodeText](../../winscript/reference/idebugdocumenthelper-addunicodetext.md)|유니코드 문자열 끝에 추가 합니다.이 문서의.|  
|[IDebugDocumentHelper::AddDBCSText](../../winscript/reference/idebugdocumenthelper-adddbcstext.md)|DBCS 문자열 끝에 추가 합니다.이 문서의.|  
|[IDebugDocumentHelper::SetDebugDocumentHost](../../winscript/reference/idebugdocumenthelper-setdebugdocumenthost.md)|집합의 `IDebugDocumentHost` 이 문서에 대 한.|  
|[IDebugDocumentHelper::AddDeferredText](../../winscript/reference/idebugdocumenthelper-adddeferredtext.md)|지정 된 텍스트를 사용할 수 있지만 문자를 제공 도우미를 알립니다.|  
|[IDebugDocumentHelper::DefineScriptBlock](../../winscript/reference/idebugdocumenthelper-definescriptblock.md)|도우미는 문자의 특정 범위 지정 된 스크립트 엔진에서 처리 하는 스크립트 블록을 나타냅니다.|  
|[IDebugDocumentHelper::SetDefaultTextAttr](../../winscript/reference/idebugdocumenthelper-setdefaulttextattr.md)|스크립트 블록에 있지 않은 텍스트를 사용 하는 기본 특성을 설정 합니다.|  
|[IDebugDocumentHelper::SetTextAttributes](../../winscript/reference/idebugdocumenthelper-settextattributes.md)|텍스트 범위의 특성을 설정합니다.|  
|[IDebugDocumentHelper::SetLongName](../../winscript/reference/idebugdocumenthelper-setlongname.md)|문서에 대 한 긴 이름을 설정합니다.|  
|[IDebugDocumentHelper::SetShortName](../../winscript/reference/idebugdocumenthelper-setshortname.md)|문서에 대 한 짧은 이름을 설정합니다.|  
|[IDebugDocumentHelper::SetDocumentAttr](../../winscript/reference/idebugdocumenthelper-setdocumentattr.md)|이 문서에 대 한 특성을 설정합니다.|  
|[IDebugDocumentHelper::GetDebugApplicationNode](../../winscript/reference/idebugdocumenthelper-getdebugapplicationnode.md)|이 문서에 해당 디버그 응용 프로그램 노드를 반환 합니다.|  
|[IDebugDocumentHelper::GetScriptBlockInfo](../../winscript/reference/idebugdocumenthelper-getscriptblockinfo.md)|문자와 해당 스크립트 블록에 스크립트 엔진의 범위를 검색 합니다.|  
|[IDebugDocumentHelper::CreateDebugDocumentContext](../../winscript/reference/idebugdocumenthelper-createdebugdocumentcontext.md)|새 디버그 문서 컨텍스트를 만듭니다.|  
|[IDebugDocumentHelper::BringDocumentToTop](../../winscript/reference/idebugdocumenthelper-bringdocumenttotop.md)|이 문서 위쪽에 디버거 사용자 인터페이스를 제공합니다.|  
|[IDebugDocumentHelper::BringDocumentContextToTop](../../winscript/reference/idebugdocumenthelper-bringdocumentcontexttotop.md)|이 문서의 컨텍스트에 위쪽으로 디버거 사용자 인터페이스에 표시 됩니다.|