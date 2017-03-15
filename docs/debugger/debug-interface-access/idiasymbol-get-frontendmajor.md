---
title: "IDiaSymbol::get_frontEndMajor | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IDiaSymbol::get_frontEndMajor 메서드"
ms.assetid: f8a067c5-3306-4fc5-bc20-8910a47ed504
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# IDiaSymbol::get_frontEndMajor
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

프런트 엔드 주 버전 번호를 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
HRESULT get_frontEndMajor (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pRetVal`  
 [out] 프런트 엔드 주 버전 번호를 반환합니다. 설명 부분을 참조하세요.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 반환 `S_FALSE` 또는 오류 코드입니다.  
  
> [!NOTE]
>  반환 값이 `S_FALSE` 속성이 해당 기호를 사용할 수 없다는 것을 의미 합니다.  
  
## <a name="remarks"></a>설명  
 컴파일러는 일반적으로 두 가지 기본 요소 이루어져: 소스 코드를 중간 형식으로 구문 분석을 처리 하는 프런트 엔드 (파서) 및 중간 폼을 어셈블리로 변환 하는 백 엔드 (코드 생성기). 다른 백 엔드 버전을 프런트 엔드 드물지 않습니다.  
  
 프런트 엔드 또는 백 엔드 버전 번호는 세 부분으로 구성 됩니다: \< 주요>. \< 부>. \< 빌드>, 여기서 \< 주요> 주 버전 번호는 \< 부> 은 부 버전 번호 및 \< 빌드> 는 빌드 번호입니다. 예를 들어 13.10.3077 합니다.  
  
## <a name="requirements"></a>요구 사항  
  
|요구 사항|설명|  
|-----------------|-----------------|  
|헤더:|dia2.h|  
|버전:|DIA SDK v 7.0|  
  
## <a name="see-also"></a>참고 항목  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)