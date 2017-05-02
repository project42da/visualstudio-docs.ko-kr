---
title: "IVariantChangeType::ChangeType | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IVariantChangeType.ChangeType
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IVariantChangeType::ChangeType"
ms.assetid: 52374764-c42e-49af-a219-ee00c535a118
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IVariantChangeType::ChangeType
Variant 값을 가져와 새로운 지정 된 형식으로 만듭니다.  
  
## 구문  
  
```  
HRESULT ChangeType(  
   VARIANT*  pvarDst,  
   VARIANT*  pvarSrc,  
   LCID  lcid,  
   VARTYPE  vtNew  
);  
```  
  
#### 매개 변수  
 `pvarDst`  
 \[in, out\] 표시 되는 값을 포함 하는 variant `pvarSrc`에 지정 된 형식으로 `vtNew`.  
  
 `pvarSrc`  
 \[in\] 새 형식으로 변경 하려면 variant 값입니다.  
  
 `lcid`  
 \[in\] 인수 문자열에서 변환할 때 사용할 로캘 컨텍스트.  
  
 `vtNew`  
 \[in\] 종류를 지정 합니다. `pvarDst` 될 수 있습니다.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
 `pvarDst` 및 `pvarSrc` 인수 수 동일 경우에 원래 값을 덮어씁니다.  이 메서드에 전달 `pvarDst` 에 `VariantClear` 함수를 고 결과적으로 `pvarDst` 올바른 값으로 초기화 되어야 합니다.  
  
## 참고 항목  
 [IVariantChangeType 인터페이스](../../winscript/reference/ivariantchangetype-interface.md)