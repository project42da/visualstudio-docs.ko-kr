---
title: IDebugGenericFieldDefinition | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: IDebugGenericFieldDefinition interface
ms.assetid: b5a853b7-221e-4d62-8948-07423089d75d
caps.latest.revision: "7"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 5ad51914225ddb8e6a558cac419d20119b286ab6
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idebuggenericfielddefinition"></a>IDebugGenericFieldDefinition
관리 코드 제네릭 형식에 대 한 필드의 정의 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDebugGenericFieldDefinition : IUnknown  
```  
  
## <a name="methods"></a>메서드  
 이 인터페이스는 다음 메서드를 구현합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[ConstructInstantiation](../../../extensibility/debugger/reference/idebuggenericfielddefinition-constructinstantiation.md)|지정 된 형식 인수 배열을 필드 인스턴스를 생성 합니다.|  
|[GetFormalTypeParams](../../../extensibility/debugger/reference/idebuggenericfielddefinition-getformaltypeparams.md)|매개 변수 개수를 지정 된 형식 매개 변수를 검색 합니다.|  
|[TypeParamCount](../../../extensibility/debugger/reference/idebuggenericfielddefinition-typeparamcount.md)|제네릭 필드와 연결 된 형식 매개 변수 수를 검색 합니다.|  
  
## <a name="requirements"></a>요구 사항  
 헤더: Sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll