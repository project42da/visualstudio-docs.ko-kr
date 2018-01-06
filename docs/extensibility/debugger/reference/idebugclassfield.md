---
title: IDebugClassField | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugClassField
helpviewer_keywords: IDebugClassField interface
ms.assetid: 49358cbc-8973-4862-9dcc-79b1248e6712
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 35566e2658ad4064b9ca3964be6ec0c76b281b7f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugclassfield"></a>IDebugClassField
이 인터페이스는 형식으로 클래스를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDebugClassField : IDebugContainerField  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 기호 공급자를 구현 하는 동일한 개체에서이 인터페이스를 구현 하는 [IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md) 인터페이스입니다. 이 인터페이스는 특수화 클래스 형식을 나타내는입니다.  
  
## <a name="notes-for-callers"></a>호출자에 대 한 참고 사항  
 인터페이스의 수는 포함 하 여이 인터페이스를 반환할 수 있는 메서드가 [IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md), [IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md), 및 [IDebugCustomAttribute](../../../extensibility/debugger/reference/idebugcustomattribute.md)합니다. 사용할 수는 또한 [QueryInterface](/cpp/atl/queryinterface) 에서이 인터페이스를 가져올 수는 [IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md) 인터페이스는 [GetKind](../../../extensibility/debugger/reference/idebugfield-getkind.md) 플래그를 반환 하는 메서드 `FIELD_TYPE_CLASS`합니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
 메서드 외에도 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) 및 [IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md) 인터페이스의 경우이 인터페이스에서 다음을 구현 합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[EnumBaseClasses](../../../extensibility/debugger/reference/idebugclassfield-enumbaseclasses.md)|이 클래스의 기본 클래스에 대 한 열거자를 만듭니다.|  
|[DoesInterfaceExist](../../../extensibility/debugger/reference/idebugclassfield-doesinterfaceexist.md)|클래스에는 특정 인터페이스는 정의 하는 경우를 결정 합니다.|  
|[EnumNestedClasses](../../../extensibility/debugger/reference/idebugclassfield-enumnestedclasses.md)|이 클래스의 중첩 된 클래스에 대 한 열거자를 만듭니다.|  
|[GetEnclosingClass](../../../extensibility/debugger/reference/idebugclassfield-getenclosingclass.md)|이 클래스를 포함 하는 클래스를 가져옵니다.|  
|[EnumInterfacesImplemented](../../../extensibility/debugger/reference/idebugclassfield-enuminterfacesimplemented.md)|이 클래스에서 구현 된 인터페이스에 대 한 열거자를 만듭니다.|  
|[EnumConstructors](../../../extensibility/debugger/reference/idebugclassfield-enumconstructors.md)|이 클래스의 생성자에 대 한 열거자를 만듭니다.|  
|[GetDefaultIndexer](../../../extensibility/debugger/reference/idebugclassfield-getdefaultindexer.md)|기본 인덱서의 이름을 가져옵니다.|  
|[EnumNestedEnums](../../../extensibility/debugger/reference/idebugclassfield-enumnestedenums.md)|이 클래스의 중첩 된 열거자에 대 한 열거자를 만듭니다.|  
  
## <a name="requirements"></a>요구 사항  
 헤더: sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [기호 공급자 인터페이스](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)   
 [IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md)