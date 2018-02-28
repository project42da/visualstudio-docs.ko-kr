---
title: "IDebugDocumentProvider 인터페이스 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- IDebugDocumentProvider interface
ms.assetid: 36510acf-1ef9-479c-a430-d3f09502f82c
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 262794718e238068cfd9a8e3fae5161b9fe8cc54
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="idebugdocumentprovider-interface"></a>IDebugDocumentProvider 인터페이스
필요에 따라 문서를 인스턴스화하는 방법을 제공 합니다.  
  
## <a name="remarks"></a>설명  
 문서를 인스턴스화하기 위한 간접 티:  
  
-   문서를를 로드할 때 필요할 수 있습니다.  
  
-   문서 개체를에 디버거 IDE 내에 포함 될 수 있습니다.  
  
-   여러 가지 방법으로 동일한 문서 개체에 액세스할 수 있습니다.  
  
 이 효과적으로 공급자에서 문서를 구분 하며 추가 런타임 컨텍스트 정보를 전달 하도록 공급자에 있습니다.  
  
 상속 된 메서드 외에도 `IDebugDocumentInfo`, `IDebugDocumentProvider` 인터페이스는 다음 메서드를 노출 합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[IDebugDocumentProvider::GetDocument](../../winscript/reference/idebugdocumentprovider-getdocument.md)|로 인해 문서가 아직 없는 경우 인스턴스화할 수 있습니다.|