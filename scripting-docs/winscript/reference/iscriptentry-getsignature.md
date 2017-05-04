---
title: "IScriptEntry::GetSignature | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IScriptEntry.GetSignature
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IScriptEntry::GetSignature"
ms.assetid: 8cbf37ac-b14c-4e15-a613-06f34857da9b
caps.latest.revision: 10
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 10
---
# IScriptEntry::GetSignature
반환에 대 한 정보를 입력은 `IScriptEntry` 함수 개체입니다.  
  
## 구문  
  
```  
HRESULT GetSignature(  
   ITypeInfo          **ppti  
   ULONG              *piMethod  
);  
```  
  
#### 매개 변수  
 `ppti`  
 \[out\] 이와 관련 된 정보를 입력 `IScriptEntry` 함수 개체입니다.  
  
 `piMethod`  
 \[out\] 방법 인덱스에는 `ITypeInfo` 개체입니다.  
  
## 반환 값  
 `HRESULT`입니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
 사용 하 여 형식 정보를 설정할 수 있습니다. [IScriptEntry::SetSignature](../../winscript/reference/iscriptentry-setsignature.md) 또는 [IScriptNode::CreateChildHandler](../../winscript/reference/iscriptnode-createchildhandler.md).  또한 내부 함수 표현에 따라 입력 하 여 형식 정보를 생성할 수 있습니다.  
  
## 참고 항목  
 [IScriptEntry 인터페이스](../../winscript/reference/iscriptentry-interface.md)