---
title: IDebugArrayObject2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: IDebugArrayObject2 interface
ms.assetid: be6e504d-4ab3-4141-a61b-0953ee0e038e
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 13e522497a0046ebfc99c60c7c3d771acfd4fbca
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugarrayobject2"></a>IDebugArrayObject2
> [!IMPORTANT]
>  Visual Studio 2015에서 구현 하는 식 계산기의 이러한 방식으로 사용 되지 않습니다. CLR 식 계산기를 구현 하는 방법에 대 한 정보를 참조 하십시오 [CLR 식 계산기](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) 및 [관리 되는 식 계산기 샘플](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample)합니다.  
  
 관리 되는 배열 개체를 나타내며 (EE) 배열에 대 한 기본 인덱스 (하위 범위)를 결정 하는 식 계산기를 허용 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDebugArrayObject2 : IDebugArrayObject  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 이 관리 되는 디버그 엔진 (DE)에 의해 구현 됩니다.  
  
## <a name="methods"></a>메서드  
 메서드 외에도 [IDebugArrayObject](../../../extensibility/debugger/reference/idebugarrayobject.md) 인터페이스,이 인터페이스는 다음 메서드를 구현 합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[GetBaseIndices](../../../extensibility/debugger/reference/idebugarrayobject2-getbaseindices.md)|배열의 차원 수를 지정 된 각 인덱스에 대 한 기본 인덱스 (하위 범위)를 검색 합니다.|  
|[HasBaseIndices](../../../extensibility/debugger/reference/idebugarrayobject2-hasbaseindices.md)|배열에 정의 된 기본 인덱스 (하위 범위)를 포함 하는 경우를 결정 합니다.|  
  
## <a name="remarks"></a>설명  
 식 계산기는 관리 되는 배열에서 구문 분석 트리를 나타내기 위해이 인터페이스를 사용 합니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: Ee.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll