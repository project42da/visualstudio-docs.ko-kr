---
title: "IDebugDocumentProvider 인터페이스 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
helpviewer_keywords: 
  - "IDebugDocumentProvider 인터페이스"
ms.assetid: 36510acf-1ef9-479c-a430-d3f09502f82c
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugDocumentProvider 인터페이스
필요에 따라 문서를 인스턴스화하는 수단을 제공 합니다.  
  
## 설명  
 인스턴스화하는 문서에 대 한 간접적인 의미:  
  
-   문서가 필요할 때 로드할 수 있습니다.  
  
-   문서 개체를 IDE 디버거 내에 포함 될 수 있습니다.  
  
-   여러 가지 방법으로 동일한 문서 개체에 액세스할 수 있습니다.  
  
 이렇게 효과적으로 문서에서 해당 공급자를 분리 하 고 추가 런타임 컨텍스트 정보를 전달 하 여 공급자 있습니다.  
  
 `IDebugDocumentInfo`에서 상속되는 메서드 외에 `IDebugDocumentProvider` 인터페이스는 다음 메서드를 노출합니다.  
  
|메서드|설명|  
|---------|--------|  
|[IDebugDocumentProvider::GetDocument](../../winscript/reference/idebugdocumentprovider-getdocument.md)|인스턴스화할 수 존재 하지 않는 문서는.|