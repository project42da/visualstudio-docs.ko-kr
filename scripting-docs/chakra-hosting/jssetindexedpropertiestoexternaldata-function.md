---
title: "JsSetIndexedPropertiesToExternalData 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: cee2d86d-ed42-4acb-86ef-95a67e63d0d6
caps.latest.revision: 2
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 2
---
# JsSetIndexedPropertiesToExternalData 함수
개체의 인덱싱된 속성을 외부 데이터로 설정합니다.  외부 데이터는 개체의 인덱싱된 속성에 대한 백업 저장소로 사용되고 형식화된 배열처럼 액세스됩니다.  
  
## 구문  
  
```  
STDAPI_(JsErrorCode) JsSetIndexedPropertiesToExternalData(  
   _In_ JsValueRef object,  
   _In_ void* data,  
   _In_ JsTypedArrayType arrayType,  
   _In_ unsigned int elementLength  
);  
```  
  
#### 매개 변수  
 `object`  
 작업할 개체입니다.  
  
 `data`  
 개체의 인덱싱된 속성에 대한 백업 저장소로 사용할 외부 데이터입니다.  
  
 `arrayType`  
 외부 데이터의 배열 요소 형식입니다.  
  
 `elementLength`  
 외부 데이터의 배열 요소 수입니다.  
  
## 반환 값  
 작업에 성공한 경우 코드 `JsNoError`이고, 그렇지 않은 경우 오류 코드입니다.  
  
## 설명  
 활성 스크립트 컨텍스트가 필요합니다.  
  
 이 API는 가장자리 모드에서만 지원됩니다.  
  
## 요구 사항  
 **헤더:** jsrt.h  
  
## 참고 항목  
 [참조\(JavaScript 런타임\)](../chakra-hosting/reference-javascript-runtime.md)