---
title: "IDiaSymbol::get_undecoratedNameEx | Microsoft Docs"
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
  - "IDiaSymbol::get_undecoratedNameEx 메서드"
ms.assetid: 579aed0b-c57d-41a1-a94a-3bf665fd4a9d
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# IDiaSymbol::get_undecoratedNameEx
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

검색 또는 일부 데코레이팅되지 않은 이름에 C\+\+ 데코레이팅된 \(링크\) 이름입니다.  
  
## 구문  
  
```cpp#  
HRESULT get_undecoratedNameEx(   
   DWORD undecorateOptions,  
   BSTR* pRetval  
);  
```  
  
#### 매개 변수  
 `undecoratedOptions`  
 \[in\] 플래그의 조합을 반환 되는 컨트롤을 지정 합니다.  특정 값과 기능에 대 한 설명 부분을 참조 하십시오.  
  
 `pRetVal`  
 \[out\] 데코레이팅되지 않은 이름에 C\+\+ 데코레이팅된 이름 반환 합니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 반환 `S_FALSE` 또는 오류 코드입니다.  
  
> [!NOTE]
>  반환 값이 `S_FALSE` 속성의 기호를 사용할 수 없음을 의미 합니다.  
  
## 설명  
 `undecorateOptions` 다음과 같은 플래그 조합을 사용할 수 있습니다.  
  
> [!NOTE]
>  선언 코드를 추가 하거나 원시 값을 사용 해야 하므로 플래그 이름 DIA SDK에 정의 되지 않습니다.  
  
|플래그|값|설명|  
|---------|-------|--------|  
|UNDNAME\_COMPLETE|0x0000|전체 undecoration 수 있습니다.|  
|UNDNAME\_NO\_LEADING\_UNDERSCORES|0x0001|키워드 확장 Microsoft에서 밑줄로 선행 제거 합니다.|  
|UNDNAME\_NO\_MS\_KEYWORDS|0x0002|키워드 확장 Microsoft 확장을 사용 하지 않습니다.|  
|UNDNAME\_NO\_FUNCTION\_RETURNS|0x0004|확장을 기본 선언의 반환 형식에 사용할 수 없습니다.|  
|UNDNAME\_NO\_ALLOCATION\_MODEL|0x0008|선언 모델의 확장을 사용할 수 없습니다.|  
|UNDNAME\_NO\_ALLOCATION\_LANGUAGE|0x0010|선언 지정자 언어의 확장을 사용할 수 없습니다.|  
|UNDNAME\_RESERVED1|0x0020|예약 되어 있습니다.|  
|UNDNAME\_RESERVED2|0x0040|예약 되어 있습니다.|  
|UNDNAME\_NO\_THISTYPE|0x0060|모든 한정자를 사용 하지 않습니다를 `this` 형식입니다.|  
|UNDNAME\_NO\_ACCESS\_SPECIFIERS|0x0080|확장을 멤버에 대 한 액세스 지정자를 사용할 수 없습니다.|  
|UNDNAME\_NO\_THROW\_SIGNATURES|0x0100|"Throw\-서명" 함수 및 함수에 대 한 포인터에 대 한 확장을 사용할 수 없습니다.|  
|UNDNAME\_NO\_MEMBER\_TYPE|0x0200|확장을 사용할 수 없습니다 `static` 또는 `virtual` 멤버입니다.|  
|UNDNAME\_NO\_RETURN\_UDT\_MODEL|0x0400|UDT 반환에 대 한 Microsoft 모델의 확장을 사용할 수 없습니다.|  
|UNDNAME\_32\_BIT\_DECODE|0x0800|32 비트 데코레이팅된 이름을 undecorates.|  
|UNDNAME\_NAME\_ONLY|0 x 1000|만 주 선언에 대 한 이름을 가져옵니다. 방금 반환 \[범위::\] 이름입니다.  템플릿 매개 변수를 확장합니다.|  
|UNDNAME\_TYPE\_ONLY|0x2000|입력 인코딩 형식 뿐입니다. 선언 된 추상 자가 작성합니다.|  
|UNDNAME\_HAVE\_PARAMETERS|0x4000|실제 템플릿 매개 변수를 사용할 수 있습니다.|  
|UNDNAME\_NO\_ECSU|0 x 8000|열거형\/클래스\/구조체\/공용 구조체를 표시 하지 않습니다.|  
|UNDNAME\_NO\_IDENT\_CHAR\_CHECK|0x10000|올바른 식별자 문자에 대 한 검사를 하지 않습니다.|  
|UNDNAME\_NO\_PTR64|0 x 20000|Ptr64 출력에 포함 되지 않습니다.|  
  
## 참고 항목  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)