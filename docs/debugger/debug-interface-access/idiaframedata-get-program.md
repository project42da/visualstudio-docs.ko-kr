---
title: "IDiaFrameData::get_program | Microsoft Docs"
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
  - "IDiaFrameData::get_program 메서드"
ms.assetid: 9201409e-b4b1-4e2e-a9f8-d17678ac538b
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# IDiaFrameData::get_program
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

현재 함수를 호출 하기 전에 설정 레지스터를 계산 하는 데 사용 되는 프로그램 문자열을 검색 합니다.  
  
## 구문  
  
```cpp#  
HRESULT get_program (   
   BSTR* pRetVal  
);  
```  
  
#### 매개 변수  
 `pRetVal`  
 \[out\] 프로그램 문자열을 반환합니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`.  반환 `S_FALSE` 이 속성이 지원 되지 않는 경우.  그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 프로그램 문자열 프롤로그를 만들기 위해 해석 되는 일련의 매크로입니다.  일반적인 스택 프레임 프로그램 문자열을 사용할 수 있습니다 예를 들어, `"$T0 $ebp = $eip $T0 4 + ^ = $ebp $T0 ^ = $esp $T0 8 + ="`.  리버스 폴란드어 표기법을 연산자는 피연산자에 따라 위치입니다.  `T0`스택에 임시 변수를 나타냅니다.  이 예제에서는 다음 단계를 수행합니다.  
  
1.  레지스터의 내용을 이동 `ebp` 에 `T0`.  
  
2.  추가 `4` 에 있는 값으로 `T0` 주소를 생성 하 고 해당 주소 로부터 값을 가져오는 값을 레지스터에 저장할 수 `eip`.  
  
3.  에 저장 된 주소에서 값을 가져오는 `T0` 레지스터에 값을 저장 하 고 `ebp`.  
  
4.  추가 `8` 에 있는 값으로 `T0` 레지스터에 값을 저장 하 고 `esp`.  
  
 Note 프로그램 문자열에 특정 cpu 호출 규칙으로 현재 스택 프레임을 표시 하는 함수에 대 한 설정입니다.  
  
## 참고 항목  
 [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)