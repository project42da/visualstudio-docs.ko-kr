---
title: "IDispError::GetSource | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IDispError.GetSource
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IDispError::GetSource"
ms.assetid: 20def54c-a67c-4102-babf-6f0704e5fc5c
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDispError::GetSource
클래스 또는 오류를 발생 시킨 응용 프로그램에 대 한 프로그래밍 언어별 식별자를 반환 합니다.  
  
## 구문  
  
```  
HRESULT GetSource(  
   BSTR*  pbstrSource  
);  
```  
  
#### 매개 변수  
 `pbstrSource`  
 \[out\] 형태로 프로그래밍 id가 들어 있는 문자열 `progname.objectname`.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
 이 메서드에 예외가 발생 클래스 또는 응용 프로그램을 확인 하는 데 사용 됩니다.  지정 된 호출 시 제공 된 로케일 식별자 \(LCID\) 언어에서 프로그래밍 식별자를 반환할 수 있습니다.  
  
> [!NOTE]
>  이 메서드가 구현되지 않은 경우  
  
## 참고 항목  
 [IDispError 인터페이스](../../winscript/reference/idisperror-interface.md)